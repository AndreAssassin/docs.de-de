---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: a94180705674c8aee3ce45607f89fdbba1c873b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757130"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="5b451-102">Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b451-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5b451-103">In anderen Beispielen dieses Abschnitts wurden Abfragen gezeigt, die Ergebnisse als eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, eine <xref:System.Collections.Generic.IEnumerable%601> von `string` und eine <xref:System.Collections.Generic.IEnumerable%601> von `int` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5b451-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="5b451-104">Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen.</span><span class="sxs-lookup"><span data-stu-id="5b451-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="5b451-105">In vielen Fällen besteht Ihr Ziel darin, dass Ihre Abfragen als eine <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b451-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b451-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b451-106">Example</span></span>  
 <span data-ttu-id="5b451-107">In diesem Beispiel wird gezeigt, wie Sie Objekte in der `Select`-Klausel instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="5b451-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="5b451-108">Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `Select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.</span><span class="sxs-lookup"><span data-stu-id="5b451-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="5b451-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b451-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="5b451-110">In diesem Beispiel wird die `M:System.Xml.Linq.XElement.Element`-Methode verwendet, die im Artikel [Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b451-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="5b451-111">Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der `M:System.Xml.Linq.XElement.Element`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5b451-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="5b451-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5b451-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b451-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b451-113">See also</span></span>

- [<span data-ttu-id="5b451-114">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b451-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
