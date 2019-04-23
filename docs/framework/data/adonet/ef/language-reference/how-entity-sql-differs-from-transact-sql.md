---
title: Unterschiede zwischen Entity SQL und Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 75ce0b00962526b76ea9f4b9fdfb0d1e1e564cdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162736"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Unterschiede zwischen Entity SQL und Transact-SQL
Dieses Thema beschreibt die Unterschiede zwischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] und [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  
  
## <a name="inheritance-and-relationships-support"></a>Unterstützung von Vererbung und Beziehungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwendet direkt konzeptionelle Entitätsschemas und unterstützt Features konzeptioneller Modelle, wie Vererbung und Beziehungen.  
  
 Bei der Vererbung ist es häufig nützlich, Instanzen eines Untertyps aus einer Auflistung von Instanzen des Obertyps auszuwählen. Die [Oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) -Operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (ähnlich wie `oftype` in C# Sequenzen) möglich.  
  
## <a name="support-for-collections"></a>Unterstützung von Auflistungen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Auflistungen als Entitäten erster Klasse. Zum Beispiel:  
  
-   In einer `from`-Klausel sind Auflistungsausdrücke gültig.  
  
-   `in` und `exists`-Unterabfragen wurden so verallgemeinert, dass sämtliche Auflistungen zulässig sind.  
  
     Eine Unterabfrage ist eine Art von Auflistung. `e1 in e2` und `exists(e)` sind die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukte zum Ausführen dieser Operationen.  
  
-   Mengenoperationen, z. B. `union`, `intersect` und `except`, verarbeiten nun Auflistungen.  
  
-   Joins verarbeiten Auflistungen.  
  
## <a name="support-for-expressions"></a>Unterstützung von Ausdrücken  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] verfügt über Unterabfragen (Tabellen) und Ausdrücke (Zeilen und Spalten).  
  
 Zur Unterstützung von Auflistungen und geschachtelten Auflistungen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alles als Ausdruck. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist zusammensetzbarer als [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], d. h., jeder Ausdruck kann überall verwendet werden. Abfrageausdrücke geben stets Auflistungen der projizierten Typen zurück und können immer verwendet werden, wenn ein Auflistungsausdruck zulässig ist. Informationen zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] Ausdrücke, die nicht unterstützt werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)], finden Sie unter [nicht unterstützte Ausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).  
  
 Bei den folgenden Abfragen handelt es sich um gültige [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen:  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Einheitliche Behandlung von Unterabfragen  
 Der Schwerpunkt auf Tabellen, erhält [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] führt Unterabfragen in Ihrem Kontext interpretiert. Beispielsweise eine Unterabfrage in der `from` Klausel gilt eine Multimenge (Tabelle). Dieselbe Unterabfrage in der `select`-Klausel wird hingegen als skalare Unterabfrage aufgefasst. Auf ähnliche Weise eine Unterabfrage, die auf der linken Seite des verwendet eine `in` Operator gilt als skalare Unterabfrage, während die rechte Seite erwartet wird ein multiset Unterabfrage sein.  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] existieren diese Unterschiede nicht. Ein Ausdruck verfügt über eine einheitliche vom Kontext unabhängige Auslegung. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] betrachtet alle Unterabfragen multimengenabfragen. Ggf. ein skalarer Wert aus der Unterabfrage wird [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bietet die `anyelement` Operator, der eine Auflistung (in diesem Fall die Unterabfrage) ausgeführt wird, extrahiert einen Singleton-Wert aus der Auflistung.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Vermeiden impliziter Koersionen für Unterabfragen  
 Ein Nebeneffekt der einheitlichen Behandlung von Unterabfragen ist die implizite Konvertierung von Unterabfragen zu skalaren Werten. In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] wird eine Multimenge von Zeilen (mit einem einzelnen Feld) implizit in einen skalaren Wert konvertiert, dessen Datentyp mit dem des Felds übereinstimmt.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt diese implizite Umwandlung nicht. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt den ANYELEMENT-Operator zum Extrahieren eines Singleton-Werts aus einer Auflistung bereit sowie eine `select value`-Klausel zur Vermeidung der Erstellung eines Zeilen-Wrappers während eines Abfrageausdrucks.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Wert auswählen: Vermeiden die impliziten Zeilen-Wrappers  
 Die select-Klausel in einer [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] -Unterabfrage erstellt implizit einen Zeilen-Wrapper für die Elemente in der Klausel. Dies bedeutet, dass keine Auflistungen von Skalaren oder Objekten erstellt werden können. [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ermöglicht eine implizite Koersion zwischen einem Zeilentyp mit einem Feld und einem Singletonwert des gleichen Datentyps an.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt die `select value`-Klausel bereit, um die implizite Zeilenkonstruktion unnötig zu machen. In einer `select value`-Klausel kann nur ein Element angegeben werden. Wenn diese Klausel verwendet wird, wird kein Zeilen-Wrapper für die Elemente in der `select`-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden. Beispiel: `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit. Mit `select` werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit folgenden Feldern:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Linkskorrelation und Aliasing  
 In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] können Ausdrücke in einem bestimmten Bereich (eine einzelne Klausel wie `select` oder `from`) nicht auf Ausdrücke verweisen, die vorher im selben Bereich definiert wurden. Einige Dialekte von SQL (einschließlich [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) unterstützen sie in der `from`-Klausel in beschränktem Umfang.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verallgemeinert Linkskorrelationen in der `from` -Klausel, und behandelt sie einheitlich. Ausdrücke in der `from`-Klausel können ohne die Verwendung zusätzlicher Syntax auf vorherige Definitionen (Definitionen auf der linken Seite) in derselben Klausel verweisen.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schränkt auch Abfragen, die `group by`-Klauseln enthalten, weiter ein. Ausdrücke in der `select` Klausel und `having` -Klausel solcher Abfragen nur bezieht sich möglicherweise auf die `group by` Schlüssel mithilfe ihrer Aliase. Das folgende Konstrukt ist in gültiger [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] jedoch nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist Folgendes zu verwenden:  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Verweisen auf Spalten (Eigenschaften) von Tabellen (Auflistungen)  
 Alle Spaltenverweise in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen mit dem Tabellenalias qualifiziert werden. Das folgende Konstrukt (vorausgesetzt, dass `a` ist eine gültige Spalte der Tabelle `T`) gilt in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] jedoch nicht in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
```  
select a from T  
```  
  
 Die Form für [!INCLUDE[esql](../../../../../../includes/esql-md.md)] lautet  
  
```  
select t.a as A from T as t  
```  
  
 Die Tabellenaliase sind in der `from`-Klausel optional. Der Name der Tabelle wird als implizites Alias verwendet. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] lässt auch das folgende Formular zu:  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a>Navigieren durch Objekte  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] verwendet die "."-Schreibweise zum Verweisen auf Spalten (Zeilen) einer Tabelle. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] erweitert diese Schreibweise (wie Programmiersprachen), um die Navigation durch Eigenschaften eines Objekts zu unterstützen.  
  
 Wenn z. B. `p` ein Ausdruck vom Typ "Person" ist, lautet die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax zum Verweisen auf die Stadt und die Adresse dieser Person wie folgt.  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a>Keine Unterstützung von *  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] unterstützt die unqualifizierte *-Syntax als Alias für die gesamte Zeile und die qualifizierte \* Syntax (t\*) als Abkürzung für die Felder dieser Tabelle. Darüber hinaus [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ermöglicht eine spezielle Anzahl (\*) Aggregat, das Nullen einschließt.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht das *-Konstrukt. [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Abfragen der Formulare `select * from T` und `select T1.* from T1, T2...` können in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als `select value t from T as t` und `select value t1 from T1 as t1, T2 as t2...` ausgedrückt werden. Außerdem behandeln diese Konstrukte Vererbung (Wertersetzbarkeit), während die `select *`-Varianten auf die Eigenschaften des deklarierten Typen auf oberster Ebene eingeschränkt sind.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nicht die `count(*)`-Aggregate. Verwenden Sie stattdessen `count(0)`.  
  
## <a name="changes-to-group-by"></a>Änderungen an "Group By"  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt Aliasing von `group by`-Schlüsseln. Ausdrücke in der `select`-Klausel und der `having`-Klausel müssen mithilfe dieser Aliase auf die `group by`-Schlüssel verweisen. Beispielsweise ist die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Syntax  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 ...entspricht folgender [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a>Auflistungsbasierte Aggregate  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Arten von Aggregaten.  
  
 Auflistungsbasierte Aggregate verarbeiten Auflistungen und erstellen das aggregierte Ergebnis. Sie können überall in der Abfrage stehen und erfordern keine `group by`-Klausel. Zum Beispiel:  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt auch Aggregate im SQL-Format. Zum Beispiel:  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a>Verwendung der "ORDER BY"-Klausel  
 In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] können ORDER BY-Klauseln nur im obersten SELECT . FROM . WHERE-Block angegeben werden. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können ORDER BY-Ausdrücke geschachtelt und überall in der Abfrage platziert werden. Die Reihenfolge in einer geschachtelten Abfrage wird jedoch nicht erhalten.  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>Bezeichner  
 In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] basiert der Bezeichnervergleich auf der Sortierreihenfolge der aktuellen Datenbank. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wird bei Bezeichnern nicht zwischen Groß-/Kleinschreibung unterschieden, Akzentzeichen werden dagegen von den keinen Akzent tragenden Zeichen unterschieden ([!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterscheidet also beispielsweise zwischen 'a' und 'ấ'). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] behandelt Buchstaben, die gleich erscheinen, aber von anderen Codepages stammen. Weitere Informationen finden Sie unter [Eingabe Zeichensatz](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Transact-SQL-Funktionalität ist in Entity SQL nicht verfügbar  
 Die folgende [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Funktionalität ist in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht verfügbar.  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bietet derzeit keine Unterstützung für DML-Anweisungen (einfügen, aktualisieren und löschen).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt in der aktuellen Version keine Unterstützung für DDL bereit.  
  
 Imperative Programmierung  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt im Gegensatz zu [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] keine Unterstützung für die imperative Programmierung bereit. Stattdessen sollte eine Programmiersprache verwendet werden.  
  
 Gruppierungsfunktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt bisher keine Gruppierungsfunktionen wie CUBE, ROLLUP und GROUPING_SET.  
  
 Analytische Funktionen  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt (bisher) keine analytischen Funktionen.  
  
 Integrierte Funktionen, Operatoren  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt eine Teilmenge der [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]der integrierten Funktionen und Operatoren. Diese Operatoren und Funktionen werden sehr wahrscheinlich von den großen Speicheranbietern unterstützt. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwendet die in einem Anbietermanifest deklarierten speicherspezifischen Funktionen an. Darüber hinaus die [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht es Ihnen, deklarieren Sie integrierte und benutzerdefinierte Speicherfunktionen für [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwenden.  
  
 Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt keine Mechanismen für Abfragehinweise bereit.  
  
 Batchabfrageergebnisse  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt keine Batchabfrageergebnisse. Beispielsweise ist Folgendes gültig [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (als Batch gesendet):  
  
```  
select * from products;  
select * from catagories;  
```  
  
 Die äquivalente Anweisung wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] jedoch nicht unterstützt:  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt nur eine Ergebnisse liefernde Abfrageanweisung pro Befehl.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Nicht unterstützte Ausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
