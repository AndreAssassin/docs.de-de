---
title: 'Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: 1b226f009776f397f73ab9ee7826484eb8869f28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780600"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="c4d98-102">Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4d98-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="c4d98-103">In diesem Thema wird gezeigt, wie Sie nach einem bestimmten Element suchen können, das ein untergeordnetes Element mit einem bestimmten Wert besitzt.</span><span class="sxs-lookup"><span data-stu-id="c4d98-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d98-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4d98-104">Example</span></span>  
 <span data-ttu-id="c4d98-105">Das Beispiel sucht nach dem `Test`-Element, das ein untergeordnetes `CommandLine`-Element mit dem Wert "Examp2.EXE" besitzt.</span><span class="sxs-lookup"><span data-stu-id="c4d98-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="c4d98-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c4d98-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 <span data-ttu-id="c4d98-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c4d98-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="c4d98-108">In diesem Beispiel verwendet die [XML Child Axis-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), und die [XML Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="c4d98-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d98-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4d98-109">Example</span></span>  
 <span data-ttu-id="c4d98-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4d98-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c4d98-111">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c4d98-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="c4d98-112">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c4d98-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c4d98-113">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c4d98-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4d98-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4d98-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="c4d98-115">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4d98-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="c4d98-116">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="c4d98-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="c4d98-117">Projektionsvorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4d98-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
