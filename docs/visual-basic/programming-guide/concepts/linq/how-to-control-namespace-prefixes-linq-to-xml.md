---
title: 'Vorgehensweise: Control-Namespace-Präfixe (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855399"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="cc999-102">Vorgehensweise: Control-Namespace-Präfixe (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cc999-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="cc999-103">In diesem Thema wird beschrieben, wie Sie Namespacepräfixe steuern können.</span><span class="sxs-lookup"><span data-stu-id="cc999-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc999-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc999-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cc999-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc999-105">Description</span></span>  
 <span data-ttu-id="cc999-106">Dieses Beispiel deklariert zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="cc999-106">This example declares two namespaces.</span></span> <span data-ttu-id="cc999-107">Gibt an, dass die `http://www.adventure-works.com` Namespace verfügt über das Präfix `aw`, und dass die `www.fourthcoffee.com` Namespace verfügt über das Präfix des `fc`.</span><span class="sxs-lookup"><span data-stu-id="cc999-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cc999-108">Code</span><span class="sxs-lookup"><span data-stu-id="cc999-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="cc999-109">Kommentare</span><span class="sxs-lookup"><span data-stu-id="cc999-109">Comments</span></span>  
 <span data-ttu-id="cc999-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cc999-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc999-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc999-111">See also</span></span>

- [<span data-ttu-id="cc999-112">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc999-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
