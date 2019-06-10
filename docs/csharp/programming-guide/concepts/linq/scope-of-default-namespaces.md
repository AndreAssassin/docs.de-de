---
title: Bereich von Standardnamespaces in C#1
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 2eee1b0c79f585710962d8e84fe584bca6b8228b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483612"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="ebbce-102">Bereich von Standardnamespaces in C\#</span><span class="sxs-lookup"><span data-stu-id="ebbce-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="ebbce-103">Standardnamespaces, wie sie in der XML-Struktur dargestellt werden, befinden sich bei Abfragen nicht innerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="ebbce-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="ebbce-104">Bei XML, das sich in einem Standardnamespace befindet, müssen Sie weiterhin eine <xref:System.Xml.Linq.XNamespace>-Variable deklarieren und diese Variable mit dem lokalen Namen kombinieren, um einen qualifizierten Namen zu erhalten, der in der Abfrage verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebbce-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="ebbce-105">Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="ebbce-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="ebbce-106">Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen, dann jedoch nicht ordnungsgemäß abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="ebbce-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="ebbce-107">Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebbce-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebbce-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebbce-108">Example</span></span>  
 <span data-ttu-id="ebbce-109">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ebbce-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ebbce-110">Code</span><span class="sxs-lookup"><span data-stu-id="ebbce-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="ebbce-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ebbce-111">Comments</span></span>  
 <span data-ttu-id="ebbce-112">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ebbce-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="ebbce-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebbce-113">Example</span></span>  
 <span data-ttu-id="ebbce-114">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.</span><span class="sxs-lookup"><span data-stu-id="ebbce-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="ebbce-115">Im Gegensatz zum falsch codierten Beispiel oben besteht der richtige Ansatz bei Verwendung von C# darin, ein <xref:System.Xml.Linq.XNamespace>-Objekt zu deklarieren und zu initialisieren und dieses beim Angeben von <xref:System.Xml.Linq.XName>-Objekten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebbce-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="ebbce-116">In diesem Fall ist das Argument der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode ein <xref:System.Xml.Linq.XName>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ebbce-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ebbce-117">Code</span><span class="sxs-lookup"><span data-stu-id="ebbce-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="ebbce-118">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ebbce-118">Comments</span></span>  
 <span data-ttu-id="ebbce-119">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="ebbce-119">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebbce-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebbce-120">See also</span></span>

- [<span data-ttu-id="ebbce-121">Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))</span><span class="sxs-lookup"><span data-stu-id="ebbce-121">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)
