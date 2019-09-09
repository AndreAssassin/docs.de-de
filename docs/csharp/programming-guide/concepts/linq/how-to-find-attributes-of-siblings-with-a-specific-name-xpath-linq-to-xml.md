---
title: 'Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 0d7842f190f7ce7869668929b69c2336d33c6183
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253738"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="11588-102">Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="11588-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="11588-103">In diesem Thema wird gezeigt, wie Sie alle Attribute der nebengeordneten Knoten des Kontextknotens ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="11588-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="11588-104">In der Auflistung werden nur Attribute mit einem bestimmten Namen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11588-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="11588-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="11588-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="11588-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11588-106">Example</span></span>  
 <span data-ttu-id="11588-107">Dieses Beispiel sucht zuerst nach einem `Book`-Element, als Nächstes nach allen nebengeordneten Elementen mit dem Namen `Book` und zum Schluss nach allen Attributen mit dem Namen `id`.</span><span class="sxs-lookup"><span data-stu-id="11588-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="11588-108">Das Ergebnis ist eine Auflistung von Attributen.</span><span class="sxs-lookup"><span data-stu-id="11588-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="11588-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="11588-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="11588-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="11588-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  