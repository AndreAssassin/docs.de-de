---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: c7dafae846a30424f008cce5f597efbdefa4bdf8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397357"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="4faf6-102">Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren</span><span class="sxs-lookup"><span data-stu-id="4faf6-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="4faf6-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.Join%2A> die <xref:System.Linq.Enumerable.GroupJoin%2A> -Methode und die-Methode verwendet werden, um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Methoden basierter Abfrage Syntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="4faf6-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="4faf6-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="4faf6-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4faf6-105">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="4faf6-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="4faf6-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="4faf6-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="4faf6-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4faf6-107">Example</span></span>  
 <span data-ttu-id="4faf6-108">Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der SalesOrderHeader-Tabelle und der SalesOrderDetail-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kunde zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4faf6-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="4faf6-109">Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="4faf6-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="4faf6-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4faf6-110">Example</span></span>  
 <span data-ttu-id="4faf6-111">Im folgenden Beispiel wird ein <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kontakt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4faf6-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="4faf6-112">Die Anzahl der Aufträge und die IDs für alle Kontakte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4faf6-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="4faf6-113">Join</span><span class="sxs-lookup"><span data-stu-id="4faf6-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="4faf6-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4faf6-114">Example</span></span>  
 <span data-ttu-id="4faf6-115">Im folgenden Beispiel werden die Tabellen Contact und SalesOrderHeader miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4faf6-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="4faf6-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4faf6-116">Example</span></span>  
 <span data-ttu-id="4faf6-117">Im folgenden Beispiel werden die Tabellen Contact und SalesOrderHeader miteinander verknüpft, und die Ergebnisse werden nach der Kontakt-ID gruppiert.</span><span class="sxs-lookup"><span data-stu-id="4faf6-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4faf6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4faf6-118">See also</span></span>

- [<span data-ttu-id="4faf6-119">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4faf6-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
