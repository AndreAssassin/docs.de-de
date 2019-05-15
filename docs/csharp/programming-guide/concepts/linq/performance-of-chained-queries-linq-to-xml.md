---
title: Leistung verketteter Abfragen (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: da01901a8c4208965a339cb3cf446f054f65638b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596853"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="868a8-102">Leistung verketteter Abfragen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="868a8-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="868a8-103">Einer der wichtigsten Vorteile von LINQ (und LINQ to XML) besteht darin, dass verkettete Abfragen wie eine einzelne große, kompliziertere Abfrage ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="868a8-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="868a8-104">Eine verkettete Abfrage ist eine Abfrage, die als Quelle eine andere Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="868a8-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="868a8-105">Beispielsweise ist im folgenden einfachen Code `query2` die Quelle von `query1`:</span><span class="sxs-lookup"><span data-stu-id="868a8-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="868a8-106">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="868a8-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="868a8-107">Diese verkettete Abfrage bietet dasselbe Leistungsprofil wie das Durchlaufen einer verknüpften Liste.</span><span class="sxs-lookup"><span data-stu-id="868a8-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
- <span data-ttu-id="868a8-108">Die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse bietet im Wesentlichen die gleiche Leistung wie das Durchlaufen einer verknüpften Liste.</span><span class="sxs-lookup"><span data-stu-id="868a8-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="868a8-109"><xref:System.Xml.Linq.XContainer.Elements%2A> wird als Iterator mit verzögerter Ausführung implementiert.</span><span class="sxs-lookup"><span data-stu-id="868a8-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="868a8-110">Dies bedeutet, dass neben dem Durchlaufen der verknüpften Liste einige zusätzliche Arbeitsschritte ausgeführt werden, z. B. die Zuweisung des Iteratorobjekts und das Nachverfolgen des Ausführungsstatus.</span><span class="sxs-lookup"><span data-stu-id="868a8-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="868a8-111">Diese Arbeitsschritte können in zwei Kategorien eingeteilt werden: einerseits die Schritte, die beim Einrichten des Iterators durchgeführt werden, und andererseits die Schritte, die in jeder Iteration durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="868a8-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="868a8-112">Zum Einrichten sind nur wenige, festgelegte Arbeitsschritte erforderlich, und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, sind proportional zur Anzahl der Elemente in der Quellauflistung.</span><span class="sxs-lookup"><span data-stu-id="868a8-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
- <span data-ttu-id="868a8-113">In `query1` wird von der Abfrage durch die `where`-Klausel die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="868a8-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="868a8-114">Diese Methode ist auch als Iterator implementiert.</span><span class="sxs-lookup"><span data-stu-id="868a8-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="868a8-115">Die Einrichtung besteht neben den normalen Einrichtungsschritten für einen Iterator aus dem Instanziieren des Delegaten, der auf den Lambdaausdruck verweist.</span><span class="sxs-lookup"><span data-stu-id="868a8-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="868a8-116">Der Delegat wird bei jeder Iteration aufgerufen, um das Prädikat auszuführen.</span><span class="sxs-lookup"><span data-stu-id="868a8-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="868a8-117">Diese Einrichtungsschritte und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, ähneln den Arbeitsschritten, die beim Durchlaufen einer Iteration der Achse durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="868a8-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
- <span data-ttu-id="868a8-118">In `query1` wird von der Abfrage durch die select<xref:System.Linq.Enumerable.Select%2A>-Klausel die -Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="868a8-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="868a8-119">Diese Methode weist dasselbe Leistungsprofil wie die <xref:System.Linq.Enumerable.Where%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="868a8-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
- <span data-ttu-id="868a8-120">In `query2` verfügen sowohl die `where`-Klausel als auch die `select`-Klausel über dasselbe Leistungsprofil wie in `query1`.</span><span class="sxs-lookup"><span data-stu-id="868a8-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="868a8-121">Die Iteration durch `query2` ist daher direkt proportional zur Anzahl der Elemente in der Quelle der ersten Abfrage, mit anderen Worten, zeitlich linear.</span><span class="sxs-lookup"><span data-stu-id="868a8-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="868a8-122">Ein entsprechendes Visual Basic-Beispiel hätte dasselbe Leistungsprofil.</span><span class="sxs-lookup"><span data-stu-id="868a8-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="868a8-123">Weitere Informationen zu Iteratoren finden Sie unter [yield](../../../../csharp/language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="868a8-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="868a8-124">Ein ausführlicheres Tutorial finden Sie unter [Tutorial: Verketten von Abfragen](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="868a8-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868a8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="868a8-125">See also</span></span>

- [<span data-ttu-id="868a8-126">Leistung (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="868a8-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
