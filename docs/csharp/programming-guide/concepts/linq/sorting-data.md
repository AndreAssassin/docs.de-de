---
title: Sortieren von Daten (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 28cf4025d0b9bca841695c9873a0ff7972726b98
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591039"
---
# <a name="sorting-data-c"></a><span data-ttu-id="c2ae8-102">Sortieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="c2ae8-102">Sorting Data (C#)</span></span>
<span data-ttu-id="c2ae8-103">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="c2ae8-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="c2ae8-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="c2ae8-106">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz:</span><span class="sxs-lookup"><span data-stu-id="c2ae8-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span> 
  
 ![Grafik, die einen alphabetischen Sortiervorgang zeigt.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="c2ae8-108">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2ae8-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="c2ae8-109">Methods</span></span>  
  
|<span data-ttu-id="c2ae8-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="c2ae8-110">Method Name</span></span>|<span data-ttu-id="c2ae8-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c2ae8-111">Description</span></span>|<span data-ttu-id="c2ae8-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="c2ae8-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="c2ae8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2ae8-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="c2ae8-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="c2ae8-114">OrderBy</span></span>|<span data-ttu-id="c2ae8-115">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="c2ae8-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c2ae8-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="c2ae8-116">OrderByDescending</span></span>|<span data-ttu-id="c2ae8-117">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="c2ae8-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c2ae8-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="c2ae8-118">ThenBy</span></span>|<span data-ttu-id="c2ae8-119">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="c2ae8-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c2ae8-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="c2ae8-120">ThenByDescending</span></span>|<span data-ttu-id="c2ae8-121">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="c2ae8-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c2ae8-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="c2ae8-122">Reverse</span></span>|<span data-ttu-id="c2ae8-123">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="c2ae8-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="c2ae8-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c2ae8-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="c2ae8-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="c2ae8-126">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="c2ae8-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="c2ae8-127">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="c2ae8-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="c2ae8-128">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="c2ae8-129">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="c2ae8-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="c2ae8-130">Im nächsten Beispiel wird veranschaulicht, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="c2ae8-131">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="c2ae8-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="c2ae8-132">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="c2ae8-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="c2ae8-133">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="c2ae8-134">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="c2ae8-135">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="c2ae8-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="c2ae8-136">Im nächsten Beispiel wird gezeigt, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="c2ae8-137">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="c2ae8-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2ae8-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ae8-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c2ae8-139">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="c2ae8-139">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="c2ae8-140">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="c2ae8-140">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="c2ae8-141">Vorgehensweise: Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="c2ae8-141">How to: Order the Results of a Join Clause</span></span>](../../linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="c2ae8-142">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c2ae8-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
