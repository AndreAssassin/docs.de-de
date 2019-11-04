---
title: 'Vorgehensweise: Generieren von Textdateien aus XML (C#)'
ms.date: 07/20/2015
ms.assetid: 9ad283f7-7cac-42ff-bf32-92aa866e6883
ms.openlocfilehash: 8e36bbda60bea207707dcf869afc059e645ec8ad
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418301"
---
# <a name="how-to-generate-text-files-from-xml-c"></a><span data-ttu-id="9d522-102">Vorgehensweise: Generieren von Textdateien aus XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9d522-102">How to: Generate Text Files from XML (C#)</span></span>
<span data-ttu-id="9d522-103">In diesem Beispiel wird gezeigt, wie Sie aus einer XML-Datei eine CSV-Datei generieren können.</span><span class="sxs-lookup"><span data-stu-id="9d522-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d522-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d522-104">Example</span></span>  
 <span data-ttu-id="9d522-105">Die C#-Version dieses Beispiels verwendet die Methodensyntax und den `Aggregate`-Operator, um aus einem XML-Dokument in einem einzelnen Ausdruck eine CSV-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9d522-105">The C# version of this example uses method syntax and the `Aggregate` operator to generate a CSV file from an XML document in a single expression.</span></span> <span data-ttu-id="9d522-106">Weitere Informationen finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="9d522-106">For more information, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="9d522-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="9d522-107">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
string csv =  
    (from el in custOrd.Element("Customers").Elements("Customer")  
    select  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}",  
            (string)el.Attribute("CustomerID"),  
            (string)el.Element("CompanyName"),  
            (string)el.Element("ContactName"),  
            (string)el.Element("ContactTitle"),  
            (string)el.Element("Phone"),  
            (string)el.Element("FullAddress").Element("Address"),  
            (string)el.Element("FullAddress").Element("City"),  
            (string)el.Element("FullAddress").Element("Region"),  
            (string)el.Element("FullAddress").Element("PostalCode"),  
            (string)el.Element("FullAddress").Element("Country"),  
            Environment.NewLine  
        )  
    )  
    .Aggregate(  
        new StringBuilder(),  
        (sb, s) => sb.Append(s),  
        sb => sb.ToString()  
    );  
Console.WriteLine(csv);  
```  
  
 <span data-ttu-id="9d522-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9d522-108">This code produces the following output:</span></span>  
  
```output  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d522-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d522-109">See also</span></span>

- [<span data-ttu-id="9d522-110">Projektionen und Transformationen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9d522-110">Projections and Transformations (LINQ to XML) (C#)</span></span>](how-to-work-with-dictionaries-using-linq-to-xml.md)
