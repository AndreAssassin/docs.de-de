---
title: 'Vorgehensweise: Ändern des Namespaces für eine vollständige XML-Struktur (C#)'
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: d046e01798c193ee0ea459f522a5c29187c697d7
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487453"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="79da6-102">Vorgehensweise: Ändern des Namespaces für eine vollständige XML-Struktur (C#)</span><span class="sxs-lookup"><span data-stu-id="79da6-102">How to: Change the Namespace for an Entire XML Tree (C#)</span></span>
<span data-ttu-id="79da6-103">Es kann passieren, dass Sie den Namespace für ein Element oder Attribut programmgesteuert ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="79da6-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="79da6-104">Mit LINQ to XML ist dies ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="79da6-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="79da6-105">Sie können die <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="79da6-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="79da6-106">Die <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>-Eigenschaft kann nicht festgelegt werden, Sie können aber problemlos die Attribute in eine <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> kopieren, die vorhandenen Attribute entfernen und dann neue Attribute hinzufügen, die sich im neuen gewünschten Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="79da6-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="79da6-107">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="79da6-107">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79da6-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79da6-108">Example</span></span>  
 <span data-ttu-id="79da6-109">Der folgende Code erstellt zwei XML-Strukturen, die sich in keinem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="79da6-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="79da6-110">Er ändert dann den Namespace beider Strukturen und fasst die Strukturen in einer gemeinsamen Struktur zusammen.</span><span class="sxs-lookup"><span data-stu-id="79da6-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="79da6-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="79da6-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
