---
title: Gruppieren von Daten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: b5a6a3795e02e0638b81824701ad0cbacbcca91a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808116"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="6db3c-102">Gruppieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6db3c-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="6db3c-103">Als „Gruppieren“ wird das Anordnen von Daten in Gruppen bezeichnet, sodass die Elemente in jeder Gruppe über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="6db3c-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="6db3c-104">Die folgende Abbildung zeigt die Ergebnisse der Gruppierung einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6db3c-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="6db3c-105">Der Schlüssel für jede Gruppe ist das Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6db3c-105">The key for each group is the character.</span></span>  
  
 ![Diagramm einen LINQ-Gruppierungsmethoden-Vorgang zeigt.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="6db3c-107">Die Methoden des Standardabfrageoperators, die Datenelemente gruppieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6db3c-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6db3c-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="6db3c-108">Methods</span></span>  
  
|<span data-ttu-id="6db3c-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="6db3c-109">Method Name</span></span>|<span data-ttu-id="6db3c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6db3c-110">Description</span></span>|<span data-ttu-id="6db3c-111">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="6db3c-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="6db3c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6db3c-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="6db3c-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="6db3c-113">GroupBy</span></span>|<span data-ttu-id="6db3c-114">Gruppenelemente, die über ein gemeinsames Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="6db3c-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="6db3c-115">Jede Gruppe wird durch ein <xref:System.Linq.IGrouping%602>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6db3c-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6db3c-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="6db3c-116">ToLookup</span></span>|<span data-ttu-id="6db3c-117">Fügt Elemente basierend auf einer Schlüsselauswahlfunktion in eine <xref:System.Linq.Lookup%602>-Klasse (one-to-many-Wörterbuch) ein.</span><span class="sxs-lookup"><span data-stu-id="6db3c-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="6db3c-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="6db3c-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="6db3c-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="6db3c-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="6db3c-120">Im folgenden Codebeispiel wird die `Group By`-Klausel angewandt, um die Gruppe ganzer Zahlen in Listen mit geraden und ungeraden Zahlen zu aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="6db3c-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="6db3c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db3c-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="6db3c-122">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6db3c-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6db3c-123">Group By-Klausel</span><span class="sxs-lookup"><span data-stu-id="6db3c-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="6db3c-124">Vorgehensweise: Dateien Gruppieren nach Erweiterung (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6db3c-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="6db3c-125">Vorgehensweise: Teilen einer Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6db3c-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
