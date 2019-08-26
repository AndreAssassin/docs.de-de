---
title: Datentransformationen mit LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: f042042f36e373ec05e8f0f15c14027463653578
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924315"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="23fd5-102">Datentransformationen mit LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="23fd5-102">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="23fd5-103">Bei [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] geht es nicht nur um das Abrufen von Daten.</span><span class="sxs-lookup"><span data-stu-id="23fd5-103">[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] is not only about retrieving data.</span></span> <span data-ttu-id="23fd5-104">Es ist auch ein leistungsstarkes Tool zur Datentransformation.</span><span class="sxs-lookup"><span data-stu-id="23fd5-104">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="23fd5-105">Mithilfe einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage können Sie eine Quellsequenz als Eingabe verwenden und sie auf viele Arten zum Erstellen einer neuen Ausgabesequenz ändern.</span><span class="sxs-lookup"><span data-stu-id="23fd5-105">By using a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="23fd5-106">Sie können die Sequenz selbst durch Sortieren und Gruppieren ändern, ohne die Elemente zu ändern.</span><span class="sxs-lookup"><span data-stu-id="23fd5-106">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="23fd5-107">Aber das vielleicht leistungsstärkste Feature von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen ist die Fähigkeit, neue Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-107">But perhaps the most powerful feature of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries is the ability to create new types.</span></span> <span data-ttu-id="23fd5-108">Dies erfolgt in der [select](../../../language-reference/keywords/select-clause.md)-Klausel.</span><span class="sxs-lookup"><span data-stu-id="23fd5-108">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="23fd5-109">Sie können z. B. folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="23fd5-109">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="23fd5-110">Führen Sie mehrere Eingabesequenzen in einer einzelnen Ausgabesequenz, die einen neuen Typ hat, zusammen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-110">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="23fd5-111">Erstellen Sie Ausgabesequenzen, deren Elemente aus nur einer oder mehreren Eigenschaften jedes Elements in der Quellsequenz bestehen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-111">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="23fd5-112">Erstellen Sie Ausgabesequenzen, deren Elemente aus Ergebnissen der Vorgänge für die Quelldaten bestehen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-112">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="23fd5-113">Erstellen Sie Ausgabesequenzen in einem anderen Format.</span><span class="sxs-lookup"><span data-stu-id="23fd5-113">Create output sequences in a different format.</span></span> <span data-ttu-id="23fd5-114">Beispielsweise können Sie Daten aus SQL-Zeilen oder Textdateien in XML umwandeln.</span><span class="sxs-lookup"><span data-stu-id="23fd5-114">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="23fd5-115">Dies sind nur einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="23fd5-115">These are just several examples.</span></span> <span data-ttu-id="23fd5-116">Natürlich können diese Transformationen auf verschiedene Weise in der gleichen Abfrage kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="23fd5-116">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="23fd5-117">Darüber hinaus kann die Ausgabesequenz einer Abfrage als Eingabesequenz für eine neue Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23fd5-117">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="23fd5-118">Verknüpfen mehrerer Eingaben in eine Ausgabesequenz</span><span class="sxs-lookup"><span data-stu-id="23fd5-118">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="23fd5-119">Sie können eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage verwenden, um eine Ausgabesequenz zu erstellen, die Elemente von mehr als einer Eingabesequenz enthält.</span><span class="sxs-lookup"><span data-stu-id="23fd5-119">You can use a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="23fd5-120">Im folgenden Beispiel wird gezeigt, wie zwei Datenstrukturen im Arbeitsspeicher kombiniert werden können, aber die gleichen Prinzipien können angewendet werden, um Daten von XML- oder SQL- oder DataSet-Quellen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="23fd5-120">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="23fd5-121">Nehmen Sie die beiden folgenden Klassentypen an:</span><span class="sxs-lookup"><span data-stu-id="23fd5-121">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="23fd5-122">Das folgende Beispiel gibt die Abfrage an:</span><span class="sxs-lookup"><span data-stu-id="23fd5-122">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="23fd5-123">Weitere Informationen finden Sie unter [join-Klausel](../../../language-reference/keywords/join-clause.md) und [select-Klausel](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="23fd5-123">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="23fd5-124">Auswählen einer Teilmenge jedes Quellelements</span><span class="sxs-lookup"><span data-stu-id="23fd5-124">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="23fd5-125">Es gibt zwei Hauptmethoden, eine Teilmenge jedes Elements in der Quellsequenz auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="23fd5-125">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="23fd5-126">Um nur einen Member des Quellelements auszuwählen, verwenden Sie die Punktoperation.</span><span class="sxs-lookup"><span data-stu-id="23fd5-126">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="23fd5-127">Im folgenden Beispiel wird angenommen, dass ein `Customer`-Objekt verschiedene öffentliche Eigenschaften enthält, einschließlich der Zeichenfolge `City`.</span><span class="sxs-lookup"><span data-stu-id="23fd5-127">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="23fd5-128">Bei der Ausführung erzeugt diese Abfrage eine Ausgabesequenz von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-128">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="23fd5-129">Zum Erstellen von Elementen, die mehr als eine Eigenschaft aus dem Quellelement enthalten, können Sie einen Objektinitialisierer mit einem benannten Objekt oder einen anonymen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="23fd5-129">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="23fd5-130">Das folgende Beispiel zeigt die Verwendung eines anonymen Typs zum Kapseln zweier Eigenschaften von jedem `Customer`-Element:</span><span class="sxs-lookup"><span data-stu-id="23fd5-130">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="23fd5-131">Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../classes-and-structs/object-and-collection-initializers.md) und [Anonyme Typen](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="23fd5-131">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="23fd5-132">Transformieren von Objekten im Speicher in XML</span><span class="sxs-lookup"><span data-stu-id="23fd5-132">Transforming in-Memory Objects into XML</span></span>  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="23fd5-133">-Abfragen machen es einfacher, Daten zwischen Datenstrukturen im Speicher, SQL-Datenbanken, ADO.NET-Datasets und XML-Streams oder XML-Dokumenten zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="23fd5-133">queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="23fd5-134">Im folgenden Beispiel werden Objekte in einer Datenstruktur im Arbeitsspeicher in XML-Elemente transformiert.</span><span class="sxs-lookup"><span data-stu-id="23fd5-134">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="23fd5-135">Der Code erzeugt die folgende XML-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23fd5-135">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="23fd5-136">Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="23fd5-136">For more information, see [Creating XML Trees in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="23fd5-137">Ausführen von Operationen für Quellelemente</span><span class="sxs-lookup"><span data-stu-id="23fd5-137">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="23fd5-138">Eine Ausgabesequenz enthält möglicherweise keine Elemente oder Elementeigenschaften aus der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="23fd5-138">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="23fd5-139">Die Ausgabe kann möglicherweise stattdessen eine Sequenz von Werten enthalten, die durch Verwendung der Quellelemente als Eingabeargumente berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="23fd5-139">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span> <span data-ttu-id="23fd5-140">Die folgende einfache Abfrage gibt, wenn sie ausgeführt wird, eine Sequenz von Zeichenfolgen aus, deren Werte eine Berechnung basierend auf der Quellsequenz der Elemente des Typs `double` darstellen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-140">The following simple query, when it is executed, outputs a sequence of strings whose values represent a calculation based on the source sequence of elements of type `double`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23fd5-141">Aufrufen von Methoden in Abfrageausdrücken wird nicht unterstützt, wenn die Abfrage in eine andere Domäne übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="23fd5-141">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="23fd5-142">Sie können beispielsweise keine normale C#-Methode in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] aufrufen, da SQL Server über keinen Kontext dafür verfügt.</span><span class="sxs-lookup"><span data-stu-id="23fd5-142">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="23fd5-143">Sie können jedoch gespeicherte Prozeduren Methoden zuordnen und diese aufrufen.</span><span class="sxs-lookup"><span data-stu-id="23fd5-143">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="23fd5-144">Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="23fd5-144">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="23fd5-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23fd5-145">See also</span></span>

- [<span data-ttu-id="23fd5-146">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="23fd5-146">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="23fd5-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="23fd5-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="23fd5-148">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="23fd5-148">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="23fd5-149">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="23fd5-149">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)
- [<span data-ttu-id="23fd5-150">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="23fd5-150">LINQ Query Expressions</span></span>](../../linq-query-expressions/index.md)
- [<span data-ttu-id="23fd5-151">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="23fd5-151">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
