---
title: Mengenvorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: cea0c0ba4dd6c7f874f69e3ec4a179248397b67d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591116"
---
# <a name="set-operations-c"></a><span data-ttu-id="47c9c-102">Mengenvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="47c9c-102">Set Operations (C#)</span></span>
<span data-ttu-id="47c9c-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="47c9c-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="47c9c-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="47c9c-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47c9c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="47c9c-105">Methods</span></span>  
  
|<span data-ttu-id="47c9c-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="47c9c-106">Method Name</span></span>|<span data-ttu-id="47c9c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="47c9c-107">Description</span></span>|<span data-ttu-id="47c9c-108">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="47c9c-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="47c9c-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47c9c-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="47c9c-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="47c9c-110">Distinct</span></span>|<span data-ttu-id="47c9c-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="47c9c-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="47c9c-112">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="47c9c-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="47c9c-113">Except</span><span class="sxs-lookup"><span data-stu-id="47c9c-113">Except</span></span>|<span data-ttu-id="47c9c-114">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="47c9c-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="47c9c-115">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="47c9c-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="47c9c-116">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="47c9c-116">Intersect</span></span>|<span data-ttu-id="47c9c-117">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="47c9c-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="47c9c-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="47c9c-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="47c9c-119">Union</span><span class="sxs-lookup"><span data-stu-id="47c9c-119">Union</span></span>|<span data-ttu-id="47c9c-120">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="47c9c-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="47c9c-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="47c9c-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="47c9c-122">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="47c9c-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="47c9c-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="47c9c-123">Distinct</span></span>  
 <span data-ttu-id="47c9c-124">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="47c9c-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="47c9c-125">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="47c9c-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="47c9c-127">Except</span><span class="sxs-lookup"><span data-stu-id="47c9c-127">Except</span></span>  
 <span data-ttu-id="47c9c-128">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47c9c-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="47c9c-129">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="47c9c-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="47c9c-130">![Grafische Darstellung der Aktion von Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except.")</span><span class="sxs-lookup"><span data-stu-id="47c9c-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="47c9c-131">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="47c9c-131">Intersect</span></span>  
 <span data-ttu-id="47c9c-132">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47c9c-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="47c9c-133">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47c9c-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a><span data-ttu-id="47c9c-135">Union</span><span class="sxs-lookup"><span data-stu-id="47c9c-135">Union</span></span>  
 <span data-ttu-id="47c9c-136">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="47c9c-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="47c9c-137">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="47c9c-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a><span data-ttu-id="47c9c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c9c-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="47c9c-140">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="47c9c-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="47c9c-141">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="47c9c-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="47c9c-142">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="47c9c-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
