---
title: Generieren von SQL aus Befehlsstrukturen – Best Practices
ms.date: 03/30/2017
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
ms.openlocfilehash: 6ac46b577f071bca6c79e23b8b77f9b267ac879b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606666"
---
# <a name="generating-sql-from-command-trees---best-practices"></a>Generieren von SQL aus Befehlsstrukturen – Best Practices

Mit Befehlsstrukturen für Ausgabeabfragen werden Abfragen so modelliert, dass diese in SQL ausgedrückt werden können. Beim Generieren von SQL anhand einer Ausgabebefehlsstruktur treten für die Anbieterwriter jedoch bestimmte allgemeine Probleme auf. Diese Probleme werden im Rahmen dieses Themas erläutert. Im nächsten Thema wird anhand des Beispielanbieters aufgezeigt, wie diese Probleme gelöst werden können.

## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a>Gruppieren von "DbExpression"-Knoten in einer SQL SELECT-Anweisung

Eine typische SQL-Anweisung verfügt über eine geschachtelte Struktur in folgender Form:

```sql
SELECT …
FROM …
WHERE …
GROUP BY …
ORDER BY …
```

Eine oder mehrere Klauseln sind möglicherweise leer.  Eine geschachtelte SELECT-Anweisung kann in allen Zeilen auftreten.

Eine mögliche Übersetzung einer Abfragebefehlsstruktur in eine SQL SELECT-Anweisung erzeugt für jeden relationalen Operatoren jeweils eine Unterabfrage. Dies führt jedoch zu unnötigen geschachtelten Unterabfragen, die nur schwer zu lesen sind.  In einigen Datenspeichern verläuft die Abfrage daher möglicherweise unbefriedigend.

Beachten Sie als Beispiel die folgende Abfragebefehlsstruktur

```
Project (
a.x,
   a = Filter(
      b.y = 5,
      b = Scan("TableA")
   )
)
```

Bei einer ineffizienten Übersetzung wird Folgendes erzeugt:

```sql
SELECT a.x
FROM (   SELECT *
         FROM TableA as b
         WHERE b.y = 5) as a
```

Beachten Sie, dass aus allen relationalen Ausdrucksknoten neue SQL SELECT-Anweisungen werden.

Daher ist es wichtig, so viele Ausdrucksknoten wie möglich in einer einzelnen SQL SELECT-Anweisung zu aggregieren, um Fehler zu vermeiden.

Das Ergebnis einer solchen Aggregation für das oben angeführte Beispiel lautet:

```sql
SELECT b.x
FROM TableA as b
WHERE b.y = 5
```

## <a name="flatten-joins-in-a-sql-select-statement"></a>Vereinfachen von Joins in einer SQL SELECT-Anweisung

Eine Möglichkeit, mehrere Knoten in einer SQL SELECT-Anweisung zu aggregieren, ist das Aggregieren mehrerer Joinausdrücke in einer einzelnen SQL SELECT-Anweisung. "DbJoinExpression" stellt einen einzelnen Join zwischen zwei Eingaben dar. Als Teil einer einzelnen SQL SELECT-Anweisung können jedoch mehrere Joins angegeben werden. In diesem Fall werden die Joins in der angegebenen Reihenfolge ausgeführt.

Linke Joinelemente (Joins, die als linke untergeordnete Elemente eines anderen Joins angezeigt werden) können einfacher in einer einzelnen SQL SELECT-Anweisung vereinfacht werden. Beachten Sie als Beispiel die folgende Abfragebefehlsstruktur:

```
InnerJoin(
   a = LeftOuterJoin(
   b = Extent("TableA")
   c = Extent("TableB")
   ON b.y = c.x ),
   d = Extent("TableC")
   ON a.b.y = d.z
)
```

Dies kann ordnungsgemäß übersetzt werden in:

```sql
SELECT *
FROM TableA as b
LEFT OUTER JOIN TableB as c ON b.y = c.x
INNER JOIN TableC as d ON b.y = d.z
```

Wenn es sich nicht um linke Joinelemente handelt, ist die Vereinfachung komplizierter und sollte daher nicht versucht werden. Beachten Sie z. B. die Joins in der folgenden Abfragebefehlsstruktur:

```
InnerJoin(
   a = Extent("TableA")
   b = LeftOuterJoin(
   c = Extent("TableB")
   d = Extent("TableC")
   ON c.y = d.x),
   ON a.z = b.c.y
)
```

Diese würden in eine SQL SELECT-Anweisung mit einer Unterabfrage übersetzt werden.

```sql
SELECT *
FROM TableA as a
INNER JOIN (SELECT *
   FROM TableB as c
   LEFT OUTER JOIN TableC as d
   ON c.y = d.x) as b
ON b.y = d.z
```

## <a name="input-alias-redirecting"></a>Eingabealiasumleitung

Beachten Sie zur Erklärung der Eingabealiasumleitung die Struktur der relationalen Ausdrücke, z. B. von "DbFilterExpression", "DbProjectExpression", "DbCrossJoinExpression", "DbJoinExpression", "DbSortExpression", "DbGroupByExpression", "DbApplyExpression" und "DbSkipExpression".

Jeder dieser Typen verfügt über mindestens eine Eingabeeigenschaft, die eine Eingabeauflistung beschreibt, sowie über eine Bindungsvariable, die den einzelnen Eingaben entspricht, die verwendet werden, um während eines Auflistungsdurchlaufs die jeweiligen Elemente dieser Eingabe darzustellen. Die Bindungsvariable wird verwendet, wenn auf das Eingabeelement verwiesen wird, z. B. in der "Predicate"-Eigenschaft von "DbFilterExpression" oder der "Projection"-Eigenschaft von "DbProjectExpression".

Beim Aggregieren mehrerer relationaler Ausdrucksknoten in einer einzelnen SQL SELECT-Anweisung und beim Auswerten eines Ausdrucks, der Teil eines relationalen Ausdrucks ist (z. B. ein Teil der „Projection“-Eigenschaft von DbProjectExpression), handelt es sich bei der verwendeten Bindungsvariable möglicherweise nicht um den Alias der Eingabe, da mehrere Ausdrucksbindungen an einen einzelnen Bereich umgeleitet werden müssen.  Dieses Problem wird als Aliasumbenennung bezeichnet.

Beachten Sie das erste Beispiel in diesem Thema. Bei der naiven Übersetzung trifft beim Übersetzen von „Projektion a.x (DbPropertyExpression(a, x))“ die Übersetzung in `a.x` zu, da der Alias der Eingabe als „a“ definiert wurde, sodass dieser mit der Bindungsvariable übereinstimmt.  Wenn jedoch beide Knoten in einer einzelnen SQL SELECT-Anweisung aggregiert werden, müssen Sie denselben "DbPropertyExpression" in `b.x` übersetzen, da der Alias der Eingabe als "b" definiert wurde.

## <a name="join-alias-flattening"></a>Joinaliasvereinfachung

Im Gegensatz zu anderen relationalen Ausdrücken einer Ausgabebefehlsstruktur gibt „DbJoinExpression“ einen Ergebnistyp aus, bei dem es sich um eine Zeile mit zwei Spalten handelt, die jeweils einer der Eingaben entsprechen. Wenn ein DbPropertyExpression erstellt wird, Zugriff auf eine skalare Eigenschaft aus einem Join stammt, ist es über eine weitere DbPropertyExpression.

Beachten Sie z. B. "a.b.y" in Beispiel 2 und "b.c.y" in Beispiel 3. In den entsprechenden SQL-Anweisungen werden diese jedoch als "b.y" bezeichnet. Dieses erneute Aliasing wird als Joinaliasvereinfachung bezeichnet.

## <a name="column-name-and-extent-alias-renaming"></a>Spaltennamen- und Blockaliasumbenennung

Wenn eine SQL SELECT-Abfrage, die einen Join enthält, mit einer Projektion abgeschlossen werden muss, kann beim Auflisten aller beteiligten Spalten der Eingaben ein Namenskonflikt auftreten, da möglicherweise mehrere Eingaben denselben Spaltennamen aufweisen. Verwenden Sie einen anderen Spaltennamen, um den Konflikt zu vermeiden.

Auch beim Vereinfachen von Joins verfügen die beteiligten Tabellen (oder Unterabfragen) möglicherweise über miteinander in Konflikt stehende Aliase, die umbenannt werden müssen.

## <a name="avoid-select-"></a>Vermeiden von SELECT *

Verwenden Sie zum Auswählen aus Basistabellen nicht `SELECT *`. Das Speichermodell einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] -Anwendung beinhaltet möglicherweise nur eine Teilmenge der Spalten, die in der Tabelle der Datenbank befinden. In diesem Fall führt `SELECT *` möglicherweise zu einem falschen Ergebnis. Stattdessen sollten Sie alle beteiligten Spalten mithilfe des Spaltennamens des Ergebnistyps der teilnehmenden Ausdrücke angeben.

## <a name="reuse-of-expressions"></a>Wiederverwendung von Ausdrücken

Ausdrücke werden möglicherweise in der von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] übergebenen Abfragebefehlsstruktur wiederverwendet. Es sollte nicht davon ausgegangen werden, dass die einzelnen Ausdrücke in der Abfragebefehlsstruktur nur einmal vorhanden sind.

## <a name="mapping-primitive-types"></a>Zuordnen von primitiven Typen

Wenn Sie konzeptionelle Typen (EDM) Anbietertypen zuordnen, sollte die Zuordnung zum allgemeinsten Typ (Int32) erfolgen, sodass alle möglichen Werte geeignet sind. Vermeiden Sie außerdem die Zuordnung zu Typen, die für viele Vorgänge, wie BLOB-Typen verwendet werden kann (z. B. `ntext` in SQL Server).

## <a name="see-also"></a>Siehe auch

- [SQL-Generierung](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
