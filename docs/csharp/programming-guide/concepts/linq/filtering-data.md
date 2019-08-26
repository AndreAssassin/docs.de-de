---
title: Filtern von Daten (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 17d3a65b6042c9679a263eff0048f5360c4aa546
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594395"
---
# <a name="filtering-data-c"></a><span data-ttu-id="dd2ab-102">Filtern von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="dd2ab-102">Filtering Data (C#)</span></span>
<span data-ttu-id="dd2ab-103">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="dd2ab-104">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="dd2ab-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="dd2ab-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Abbildung zu einem LINQ-Filtervorgang](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="dd2ab-108">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd2ab-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="dd2ab-109">Methods</span></span>  
  
|<span data-ttu-id="dd2ab-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="dd2ab-110">Method Name</span></span>|<span data-ttu-id="dd2ab-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dd2ab-111">Description</span></span>|<span data-ttu-id="dd2ab-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="dd2ab-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="dd2ab-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd2ab-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="dd2ab-114">OfType</span><span class="sxs-lookup"><span data-stu-id="dd2ab-114">OfType</span></span>|<span data-ttu-id="dd2ab-115">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="dd2ab-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="dd2ab-117">Where</span><span class="sxs-lookup"><span data-stu-id="dd2ab-117">Where</span></span>|<span data-ttu-id="dd2ab-118">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="dd2ab-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="dd2ab-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="dd2ab-120">Im folgenden Beispiel wird die `where`-Klausel verwendet, um die Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dd2ab-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd2ab-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd2ab-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="dd2ab-122">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="dd2ab-122">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="dd2ab-123">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="dd2ab-123">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="dd2ab-124">Vorgehensweise: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="dd2ab-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="dd2ab-125">Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="dd2ab-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="dd2ab-126">Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#)</span><span class="sxs-lookup"><span data-stu-id="dd2ab-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="dd2ab-127">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="dd2ab-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
