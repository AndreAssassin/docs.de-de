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
# <a name="select-clause-c-reference"></a><span data-ttu-id="91b29-102">select-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="91b29-102">select clause (C# Reference)</span></span>

<span data-ttu-id="91b29-103">In einem Abfrageausdruck gibt die `select`-Klausel den Typ der Werte an, die beim Ausführen der Abfrage erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="91b29-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="91b29-104">Das Ergebnis basiert auf der Auswertung aller vorherigen Klauseln und auf allen Ausdrücke in der `select`-Klausel selbst.</span><span class="sxs-lookup"><span data-stu-id="91b29-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="91b29-105">Ein Abfrageausdruck muss entweder mit einer `select`-Klausel oder einer [group](group-clause.md)-Klausel enden.</span><span class="sxs-lookup"><span data-stu-id="91b29-105">A query expression must terminate with either a `select` clause or a [group](group-clause.md) clause.</span></span>

<span data-ttu-id="91b29-106">Im folgenden Beispiel wird eine einfache `select`-Klausel in einem Abfrageausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="91b29-106">The following example shows a simple `select` clause in a query expression.</span></span>

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

<span data-ttu-id="91b29-107">Der Typ der mit der `select`-Klausel erstellten Sequenz bestimmt den Typ der Abfragevariable `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="91b29-107">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="91b29-108">Im einfachsten Fall gibt die `select`-Klausel nur die Bereichsvariable an.</span><span class="sxs-lookup"><span data-stu-id="91b29-108">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="91b29-109">Dadurch enthält die zurückgegebene Sequenz Elemente desselben Typs wie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="91b29-109">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="91b29-110">Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-110">For more information, see [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="91b29-111">Allerdings bietet die `select`-Klausel zudem ein leistungsstarkes Werkzeug, um Quelldaten in neue Typen zu transformieren (oder zu *projizieren*).</span><span class="sxs-lookup"><span data-stu-id="91b29-111">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="91b29-112">Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-112">For more information, see [Data Transformations with LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="91b29-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91b29-113">Example</span></span>

<span data-ttu-id="91b29-114">Das folgende Beispiel zeigt die verschiedenen Formen, die eine `select`-Klausel annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="91b29-114">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="91b29-115">Beachten Sie in jeder Abfrage die Beziehung zwischen der `select`-Klausel und dem Typ der *Abfragevariable* (`studentQuery1`, `studentQuery2` usw.).</span><span class="sxs-lookup"><span data-stu-id="91b29-115">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

<span data-ttu-id="91b29-116">Wie in `studentQuery8` im vorherigen Beispiel kann es möglicherweise sinnvoll sein, dass die Elemente der zurückgegebenen Sequenz nur eine Teilmenge der Eigenschaften der Quellelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="91b29-116">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="91b29-117">Indem die zurückgegebene Sequenz so klein wie möglich gehalten wird, können die Speicheranforderungen reduziert und die Geschwindigkeit der Abfrageausführung erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="91b29-117">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="91b29-118">Erstellen Sie hierzu einen anonymen Typ in der `select`-Klausel, und verwenden Sie einen Objektinitialisierer, um sie mit den entsprechenden Eigenschaften aus dem Quellelement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="91b29-118">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="91b29-119">Ein Beispiel zur Vorgehensweise finden Sie unter [Objekt- und Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-119">For an example of how to do this, see [Object and Collection Initializers](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="91b29-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91b29-120">Remarks</span></span>

<span data-ttu-id="91b29-121">Beim Kompilieren wird die `select`-Klausel in einen Methodenaufruf des <xref:System.Linq.Enumerable.Select%2A>-Standardabfrageoperators übersetzt.</span><span class="sxs-lookup"><span data-stu-id="91b29-121">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="91b29-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91b29-122">See also</span></span>

- [<span data-ttu-id="91b29-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="91b29-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="91b29-124">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="91b29-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="91b29-125">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="91b29-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="91b29-126">partial (Methode) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="91b29-126">partial (Method) (C# Reference)</span></span>](partial-method.md)
- [<span data-ttu-id="91b29-127">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="91b29-127">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="91b29-128">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="91b29-128">LINQ Query Expressions</span></span>](../../programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="91b29-129">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="91b29-129">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
