---
title: Datentypen werden umgerechnet (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 744dec0093384a15470186fc09695c17e79468fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524229"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="8c234-102">Datentypen werden umgerechnet (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c234-102">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="8c234-103">Konvertierungsmethoden ändern den Typ von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="8c234-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="8c234-104">Konvertierungsvorgänge in LINQ-Abfragen sind in vielen Anwendungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="8c234-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="8c234-105">Im folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8c234-105">The following are some examples:</span></span>

- <span data-ttu-id="8c234-106">Die <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>-Methode kann zum Ausblenden einer benutzerdefinierten Implementierung eines Standardabfrageoperators eines Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c234-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="8c234-107">Die <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType>-Methode kann verwendet werden, um nicht parametrisierte Auflistungen für LINQ-Abfragen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8c234-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="8c234-108">Die Methoden <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> und <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> können verwendet werden, um die sofortige Ausführung einer Abfrage zu erzwingen, statt sie zu verzögern, bis die Abfrage enumeriert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c234-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="8c234-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="8c234-109">Methods</span></span>

<span data-ttu-id="8c234-110">Die folgende Tabelle enthält die Standardabfrageoperator-Methoden, die Datentypumwandlungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c234-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="8c234-111">Die Konvertierungsmethoden in dieser Tabelle, deren Namen mit „As“ beginnen, ändern den statischen Typ der Quellauflistung, listen ihn jedoch nicht auf.</span><span class="sxs-lookup"><span data-stu-id="8c234-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="8c234-112">Die Methoden, deren Namen mit „To“ anfangen, listen die Quellauflistung auf und verschieben die Elemente in den entsprechenden Auflistungstyp.</span><span class="sxs-lookup"><span data-stu-id="8c234-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="8c234-113">Methodenname</span><span class="sxs-lookup"><span data-stu-id="8c234-113">Method Name</span></span>|<span data-ttu-id="8c234-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c234-114">Description</span></span>|<span data-ttu-id="8c234-115">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="8c234-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="8c234-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c234-116">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="8c234-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="8c234-117">AsEnumerable</span></span>|<span data-ttu-id="8c234-118">Gibt die Eingabe als <xref:System.Collections.Generic.IEnumerable%601> typisiert zurück</span><span class="sxs-lookup"><span data-stu-id="8c234-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="8c234-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="8c234-120">AsQueryable</span></span>|<span data-ttu-id="8c234-121">Konvertiert ein (generisches) <xref:System.Collections.IEnumerable>-Element in ein (generisches) <xref:System.Linq.IQueryable>-Element</span><span class="sxs-lookup"><span data-stu-id="8c234-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="8c234-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-123">Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="8c234-123">Cast</span></span>|<span data-ttu-id="8c234-124">Kopiert die Elemente einer Auflistung in einen bestimmten Typ.</span><span class="sxs-lookup"><span data-stu-id="8c234-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-125">OfType</span><span class="sxs-lookup"><span data-stu-id="8c234-125">OfType</span></span>|<span data-ttu-id="8c234-126">Filtert Werte, je nach ihrer Fähigkeit, die in einen angegebenen Typ umgewandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c234-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="8c234-127">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="8c234-128">ToArray</span></span>|<span data-ttu-id="8c234-129">Konvertiert eine Auflistung in ein Array.</span><span class="sxs-lookup"><span data-stu-id="8c234-129">Converts a collection to an array.</span></span> <span data-ttu-id="8c234-130">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8c234-130">This method forces query execution.</span></span>|<span data-ttu-id="8c234-131">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="8c234-132">ToDictionary</span></span>|<span data-ttu-id="8c234-133">Platziert Elemente in ein <xref:System.Collections.Generic.Dictionary%602> auf Grundlage einer Schlüsselauswahlfunktion.</span><span class="sxs-lookup"><span data-stu-id="8c234-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="8c234-134">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8c234-134">This method forces query execution.</span></span>|<span data-ttu-id="8c234-135">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-136">ToList</span><span class="sxs-lookup"><span data-stu-id="8c234-136">ToList</span></span>|<span data-ttu-id="8c234-137">Konvertiert eine Auflistung in eine <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="8c234-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="8c234-138">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8c234-138">This method forces query execution.</span></span>|<span data-ttu-id="8c234-139">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="8c234-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="8c234-140">ToLookup</span></span>|<span data-ttu-id="8c234-141">Platziert Elemente, basierend auf einer Schlüsselauswahlfunktion, in ein <xref:System.Linq.Lookup%602> (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="8c234-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="8c234-142">Diese Methode erzwingt die Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="8c234-142">This method forces query execution.</span></span>|<span data-ttu-id="8c234-143">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="8c234-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="8c234-144">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="8c234-144">Query Expression Syntax Example</span></span>

<span data-ttu-id="8c234-145">Im folgenden Codebeispiel wird die `From As`-Klausel verwendet, um einen Typ in einen Untertyp umzuwandeln, bevor auf einen Member zugegriffen wird, der nur für den Untertyp verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8c234-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="8c234-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c234-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="8c234-147">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="8c234-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="8c234-148">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="8c234-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8c234-149">Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c234-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
