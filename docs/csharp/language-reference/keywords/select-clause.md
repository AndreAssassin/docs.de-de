---
title: select-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: 3ba52fccc0521df1a0bb5b6177575dc5d2152248
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633820"
---
# <a name="select-clause-c-reference"></a>select-Klausel (C#-Referenz)

In einem Abfrageausdruck gibt die `select`-Klausel den Typ der Werte an, die beim Ausführen der Abfrage erstellt werden. Das Ergebnis basiert auf der Auswertung aller vorherigen Klauseln und auf allen Ausdrücke in der `select`-Klausel selbst. Ein Abfrageausdruck muss entweder mit einer `select`-Klausel oder einer [group](group-clause.md)-Klausel enden.

Im folgenden Beispiel wird eine einfache `select`-Klausel in einem Abfrageausdruck dargestellt.

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

Der Typ der mit der `select`-Klausel erstellten Sequenz bestimmt den Typ der Abfragevariable `queryHighScores`. Im einfachsten Fall gibt die `select`-Klausel nur die Bereichsvariable an. Dadurch enthält die zurückgegebene Sequenz Elemente desselben Typs wie die Datenquelle. Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Allerdings bietet die `select`-Klausel zudem ein leistungsstarkes Werkzeug, um Quelldaten in neue Typen zu transformieren (oder zu *projizieren*). Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die verschiedenen Formen, die eine `select`-Klausel annehmen kann. Beachten Sie in jeder Abfrage die Beziehung zwischen der `select`-Klausel und dem Typ der *Abfragevariable* (`studentQuery1`, `studentQuery2` usw.).

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

Wie in `studentQuery8` im vorherigen Beispiel kann es möglicherweise sinnvoll sein, dass die Elemente der zurückgegebenen Sequenz nur eine Teilmenge der Eigenschaften der Quellelemente enthalten. Indem die zurückgegebene Sequenz so klein wie möglich gehalten wird, können die Speicheranforderungen reduziert und die Geschwindigkeit der Abfrageausführung erhöht werden. Erstellen Sie hierzu einen anonymen Typ in der `select`-Klausel, und verwenden Sie einen Objektinitialisierer, um sie mit den entsprechenden Eigenschaften aus dem Quellelement zu initialisieren. Ein Beispiel zur Vorgehensweise finden Sie unter [Objekt- und Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="remarks"></a>Hinweise

Beim Kompilieren wird die `select`-Klausel in einen Methodenaufruf des <xref:System.Linq.Enumerable.Select%2A>-Standardabfrageoperators übersetzt.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Abfrageschlüsselwörter (LINQ)](query-keywords.md)
- [from-Klausel](from-clause.md)
- [partial (Methode) (C#-Referenz)](partial-method.md)
- [Anonyme Typen](../../programming-guide/classes-and-structs/anonymous-types.md)
- [LINQ-Abfrageausdrücke](../../programming-guide/linq-query-expressions/index.md)
- [Erste Schritte mit LINQ in C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)
