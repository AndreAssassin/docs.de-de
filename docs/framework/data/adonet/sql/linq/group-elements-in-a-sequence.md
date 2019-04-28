---
title: Gruppieren von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: 5d812ae9b5fd0a796588d3366b8546ef84c982c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877356"
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="311f7-102">Gruppieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="311f7-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="311f7-103">Der <xref:System.Linq.Enumerable.GroupBy%2A>-Operator gruppiert die Elemente einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="311f7-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="311f7-104">In den folgenden Beispielen wird die Datenbank Northwind verwendet.</span><span class="sxs-lookup"><span data-stu-id="311f7-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="311f7-105">NULL-Spaltenwerte in <xref:System.Linq.Enumerable.GroupBy%2A>-Abfragen können manchmal eine <xref:System.InvalidOperationException> auslösen.</span><span class="sxs-lookup"><span data-stu-id="311f7-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="311f7-106">Weitere Informationen finden Sie im Abschnitt "GroupBy InvalidOperationException" [Problembehandlung](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="311f7-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="311f7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-107">Example</span></span>  
 <span data-ttu-id="311f7-108">Im folgenden Beispiel wird `Products` nach `CategoryID` partitioniert.</span><span class="sxs-lookup"><span data-stu-id="311f7-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="311f7-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-109">Example</span></span>  
 <span data-ttu-id="311f7-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Max%2A> verwendet, um den maximalen Einzelpreis für jede `CategoryID` zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="311f7-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="311f7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-111">Example</span></span>  
 <span data-ttu-id="311f7-112">Im folgenden Beispiel wird Average verwendet, um den durchschnittlichen `UnitPrice` für jede `CategoryID` zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="311f7-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="311f7-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-113">Example</span></span>  
 <span data-ttu-id="311f7-114">Im folgenden Beispiel wird <xref:System.Linq.Queryable.Sum%2A> verwendet, um den gesamten `UnitPrice` für jede `CategoryID` zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="311f7-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="311f7-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-115">Example</span></span>  
 <span data-ttu-id="311f7-116">Im folgenden Beispiel wird <xref:System.Linq.Queryable.Count%2A> verwendet, um die Anzahl eingestellter `Products` in jeder `CategoryID` zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="311f7-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="311f7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-117">Example</span></span>  
 <span data-ttu-id="311f7-118">Im folgenden Beispiel wird eine `where`-Klausel verwendet, um alle Kategorien mit mindesten zehn Produkten zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="311f7-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="311f7-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-119">Example</span></span>  
 <span data-ttu-id="311f7-120">Im folgenden Beispiel werden Produkte nach `CategoryID` und `SupplierID` gruppiert.</span><span class="sxs-lookup"><span data-stu-id="311f7-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="311f7-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-121">Example</span></span>  
 <span data-ttu-id="311f7-122">Im folgenden Beispiel werden zwei Produktsequenzen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="311f7-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="311f7-123">Die erste Sequenz enthält Produkte mit einem Einzelpreis von 10 oder weniger.</span><span class="sxs-lookup"><span data-stu-id="311f7-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="311f7-124">Die zweite Sequenz enthält Produkte mit einem Einzelpreis von mehr als 10.</span><span class="sxs-lookup"><span data-stu-id="311f7-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="311f7-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="311f7-125">Example</span></span>  
 <span data-ttu-id="311f7-126">Der <xref:System.Linq.Queryable.GroupBy%2A>-Operator kann nur ein einzelnes Hauptargument annehmen.</span><span class="sxs-lookup"><span data-stu-id="311f7-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="311f7-127">Wenn Sie eine Gruppierung nach mehreren Schlüsseln benötigen, müssen Sie einen anonymen Typ erstellen. Siehe hierzu das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="311f7-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="311f7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="311f7-128">See also</span></span>

- [<span data-ttu-id="311f7-129">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="311f7-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="311f7-130">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="311f7-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
