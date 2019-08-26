---
title: Gruppieren von Daten (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 15dafdb144ee9fd4184d4c8281d041e03161a16b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594199"
---
# <a name="grouping-data-c"></a><span data-ttu-id="ac170-102">Gruppieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="ac170-102">Grouping Data (C#)</span></span>
<span data-ttu-id="ac170-103">Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="ac170-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="ac170-104">Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ac170-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="ac170-105">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ac170-105">The key for each group is the character.</span></span>  
  
 ![Diagramm, das eine LINQ-Gruppierung zeigt.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="ac170-107">Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac170-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac170-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="ac170-108">Methods</span></span>  
  
|<span data-ttu-id="ac170-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="ac170-109">Method Name</span></span>|<span data-ttu-id="ac170-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac170-110">Description</span></span>|<span data-ttu-id="ac170-111">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ac170-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="ac170-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac170-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ac170-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="ac170-113">GroupBy</span></span>|<span data-ttu-id="ac170-114">Gruppenelemente, die über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="ac170-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="ac170-115">Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ac170-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="ac170-116">Oder</span><span class="sxs-lookup"><span data-stu-id="ac170-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ac170-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="ac170-117">ToLookup</span></span>|<span data-ttu-id="ac170-118">Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="ac170-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="ac170-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="ac170-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="ac170-120">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ac170-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="ac170-121">Im folgenden Codebeispiel wird die `group by`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="ac170-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac170-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac170-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ac170-123">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="ac170-123">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="ac170-124">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="ac170-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="ac170-125">Vorgehensweise: Erstellen einer geschachtelten Gruppe</span><span class="sxs-lookup"><span data-stu-id="ac170-125">How to: Create a Nested Group</span></span>](../../linq-query-expressions/how-to-create-a-nested-group.md)
- [<span data-ttu-id="ac170-126">Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ac170-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="ac170-127">Vorgehensweise: Gruppieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="ac170-127">How to: Group Query Results</span></span>](../../linq-query-expressions/how-to-group-query-results.md)
- [<span data-ttu-id="ac170-128">Vorgehensweise: Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="ac170-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="ac170-129">Vorgehensweise: Teilen einer Datei in mehrere Dateien durch Verwenden von Gruppen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ac170-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
