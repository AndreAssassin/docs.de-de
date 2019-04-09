---
title: Zurückgeben oder Überspringen von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 885e6bc011041320a3dc7b17d84b2541bf030adf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168310"
---
# <a name="return-or-skip-elements-in-a-sequence"></a><span data-ttu-id="6a5d9-102">Zurückgeben oder Überspringen von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="6a5d9-102">Return Or Skip Elements in a Sequence</span></span>
<span data-ttu-id="6a5d9-103">Verwenden Sie den <xref:System.Linq.Queryable.Take%2A>-Operator, um eine bestimmte Anzahl von Elementen in einer Sequenz zurückzugeben und den Rest zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-103">Use the <xref:System.Linq.Queryable.Take%2A> operator to return a given number of elements in a sequence and then skip over the remainder.</span></span>  
  
 <span data-ttu-id="6a5d9-104">Verwenden Sie den <xref:System.Linq.Queryable.Skip%2A>-Operator um eine bestimmte Anzahl von Elementen in einer Sequenz zu überspringen und den Rest zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-104">Use the <xref:System.Linq.Queryable.Skip%2A> operator to skip over a given number of elements in a sequence and then return the remainder.</span></span>  
  
> [!NOTE]
>  <xref:System.Linq.Enumerable.Take%2A> <span data-ttu-id="6a5d9-105">und <xref:System.Linq.Enumerable.Skip%2A> weisen bestimmte Einschränkungen, wenn sie in Abfragen mit SQL Server 2000 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-105">and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="6a5d9-106">Weitere Informationen finden Sie im Eintrag "Überspringen und Behandeln von Ausnahmen in SQLServer 2000" in [Problembehandlung](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="6a5d9-106">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6a5d9-107">übersetzt <xref:System.Linq.Queryable.Skip%2A> mithilfe einer Unterabfrage mit SQL `NOT EXISTS` Klausel.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-107">translates <xref:System.Linq.Queryable.Skip%2A> by using a subquery with the SQL `NOT EXISTS` clause.</span></span> <span data-ttu-id="6a5d9-108">Diese Übersetzung weist die folgenden Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-108">This translation has the following limitations:</span></span>  
  
-   <span data-ttu-id="6a5d9-109">Das Argument muss ein Satz sein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-109">The argument must be a set.</span></span> <span data-ttu-id="6a5d9-110">Multisets werden nicht unterstützt, auch dann nicht, wenn diese geordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-110">Multisets are not supported, even if ordered.</span></span>  
  
-   <span data-ttu-id="6a5d9-111">Die erzeugte Abfrage kann wesentlich komplexer sein als die Abfrage, die für die Basisabfrage erstellt wurde, auf die <xref:System.Linq.Queryable.Skip%2A> angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-111">The generated query can be much more complex than the query generated for the base query on which <xref:System.Linq.Queryable.Skip%2A> is applied.</span></span> <span data-ttu-id="6a5d9-112">Diese Komplexität kann zu einer Abnahme der Leistung oder sogar zu einer Zeitüberschreitung führen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-112">This complexity can cause decrease in performance or even a time-out.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a5d9-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a5d9-113">Example</span></span>  
 <span data-ttu-id="6a5d9-114">Im folgenden Beispiel wird `Take` verwendet, um die ersten fünf eingestellten `Employees` auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-114">The following example uses `Take` to select the first five `Employees` hired.</span></span> <span data-ttu-id="6a5d9-115">Beachten Sie, dass die Auflistung zuerst nach `HireDate` sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-115">Note that the collection is first sorted by `HireDate`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="6a5d9-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a5d9-116">Example</span></span>  
 <span data-ttu-id="6a5d9-117">Im folgenden Beispiel wird <xref:System.Linq.Queryable.Skip%2A> verwendet, um alle außer den zehn teuersten `Products` auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-117">The following example uses <xref:System.Linq.Queryable.Skip%2A> to select all except the 10 most expensive `Products`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="6a5d9-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a5d9-118">Example</span></span>  
 <span data-ttu-id="6a5d9-119">Im folgenden Beispiel werden die <xref:System.Linq.Queryable.Skip%2A>-Methode und die <xref:System.Linq.Queryable.Take%2A>-Methode kombiniert, um die ersten 50 Datensätze zu überspringen und dann die nächsten zehn zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-119">The following example combines the <xref:System.Linq.Queryable.Skip%2A> and <xref:System.Linq.Queryable.Take%2A> methods to skip the first 50 records and then return the next 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 <xref:System.Linq.Queryable.Take%2A> <span data-ttu-id="6a5d9-120">und <xref:System.Linq.Queryable.Skip%2A> Vorgänge sind nur bei geordneten Sätzen gut definiert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-120">and <xref:System.Linq.Queryable.Skip%2A> operations are well defined only against ordered sets.</span></span> <span data-ttu-id="6a5d9-121">Die Semantik für ungeordnete Sätze oder Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-121">The semantics for unordered sets or multisets is undefined.</span></span>  
  
 <span data-ttu-id="6a5d9-122">Aufgrund der Sortierungseinschränkungen in SQL versucht [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], die Sortierung des Arguments des <xref:System.Linq.Queryable.Take%2A>-Operators oder des <xref:System.Linq.Queryable.Skip%2A>-Operators auf das Operatorergebnis zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-122">Because of the limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of the <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> operator to the result of the operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a5d9-123">Die Übersetzung weicht für [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] und [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)] ab.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-123">Translation is different for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] and [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span> <span data-ttu-id="6a5d9-124">Wenn Sie planen, <xref:System.Linq.Queryable.Skip%2A> mit einer komplexeren Abfrage einzusetzen, verwenden Sie [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a5d9-124">If you plan to use <xref:System.Linq.Queryable.Skip%2A> with a query of any complexity, use [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].</span></span>  
  
 <span data-ttu-id="6a5d9-125">Beachten Sie die folgende [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-125">Consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6a5d9-126">Verschiebt die Sortierung bis zum Ende in der SQL-Code wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6a5d9-126">moves the ordering to the end in the SQL code, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="6a5d9-127">Wenn <xref:System.Linq.Queryable.Take%2A> und <xref:System.Linq.Queryable.Skip%2A> verkettet werden, muss die angegebene Sortierung konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-127">When <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are chained together, all the specified ordering must be consistent.</span></span> <span data-ttu-id="6a5d9-128">Andernfalls sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-128">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="6a5d9-129">Für nicht negative, konstante, ganzzahlige Argumente auf Grundlage der SQL-Spezifikation sind <xref:System.Linq.Queryable.Take%2A> und <xref:System.Linq.Queryable.Skip%2A> klar definiert.</span><span class="sxs-lookup"><span data-stu-id="6a5d9-129">For non-negative, constant integral arguments based on the SQL specification, both <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are well-defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5d9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a5d9-130">See also</span></span>

- [<span data-ttu-id="6a5d9-131">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="6a5d9-131">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="6a5d9-132">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="6a5d9-132">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
