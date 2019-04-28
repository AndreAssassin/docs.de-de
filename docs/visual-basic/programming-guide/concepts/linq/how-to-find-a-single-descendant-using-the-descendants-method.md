---
title: 'Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0c03468c-efc8-4140-98f3-fb67acd9e8e1
ms.openlocfilehash: 0a2574422f95ed4d2b82c33ee999b233d95ea398
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855595"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-visual-basic"></a><span data-ttu-id="5ef29-102">Vorgehensweise: Suchen eines einzelnen Nachfolgers mit der Descendants-Methode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ef29-102">How to: Find a Single Descendant Using the Descendants Method (Visual Basic)</span></span>
<span data-ttu-id="5ef29-103">Mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achsenmethode können Sie schnell Code zum Suchen nach einem einzelnen eindeutig benannten Element schreiben.</span><span class="sxs-lookup"><span data-stu-id="5ef29-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="5ef29-104">Diese Technik ist besonders nützlich, wenn Sie einen bestimmten Nachfolger mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="5ef29-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="5ef29-105">Sie könnten den Code zwar so schreiben, dass eine Navigation zum gewünschten Element erfolgt, es ist aber häufig schneller und einfacher, den Code mit der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="5ef29-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ef29-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ef29-106">Example</span></span>  
 <span data-ttu-id="5ef29-107">In diesem Beispiel wird der <xref:System.Linq.Enumerable.First%2A>-Standardabfrageoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ef29-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1>GC1 Value</GrandChild1>  
        </Child1>  
        <Child2>  
            <GrandChild2>GC2 Value</GrandChild2>  
        </Child2>  
        <Child3>  
            <GrandChild3>GC3 Value</GrandChild3>  
        </Child3>  
        <Child4>  
            <GrandChild4>GC4 Value</GrandChild4>  
        </Child4>  
    </Root>  
Dim grandChild3 As String = _  
    (From el In root...<GrandChild3> _  
    Select el).First()  
Console.WriteLine(grandChild3)  
```  
  
 <span data-ttu-id="5ef29-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5ef29-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="5ef29-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ef29-109">Example</span></span>  
 <span data-ttu-id="5ef29-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ef29-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="5ef29-111">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="5ef29-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child1>  
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
                </aw:Child1>  
                <aw:Child2>  
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
                </aw:Child2>  
                <aw:Child3>  
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
                </aw:Child3>  
                <aw:Child4>  
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
                </aw:Child4>  
            </aw:Root>  
        Dim grandChild3 As String = _  
            (From el In root...<aw:GrandChild3> _  
            Select el).First()  
        Console.WriteLine(grandChild3)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="5ef29-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5ef29-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ef29-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ef29-113">See also</span></span>

- [<span data-ttu-id="5ef29-114">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ef29-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
