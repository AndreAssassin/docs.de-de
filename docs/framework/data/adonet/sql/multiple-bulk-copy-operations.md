---
title: Mehrere Massenkopiervorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 8ee0fdbfc167c819942d8282aca56b7c5168fd87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946850"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="47599-102">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="47599-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="47599-103">Sie können mehrere Massenkopiervorgänge mithilfe einer einzigen Instanz der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse durchführen.</span><span class="sxs-lookup"><span data-stu-id="47599-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="47599-104">Wenn sich die Vorgangs Parameter zwischen den Kopien ändern (z. b. dem Namen der Ziel Tabelle), müssen Sie diese vor allen nachfolgenden Aufrufen einer der Methoden " **Write-toserver** " aktualisieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="47599-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="47599-105">Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte wie im vorherigen Massenkopiervorgang einer angegebenen Instanz erhalten.</span><span class="sxs-lookup"><span data-stu-id="47599-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47599-106">Es ist effizienter, mehrere Massenkopiervorgänge mithilfe derselben Instanz der <xref:System.Data.SqlClient.SqlBulkCopy> durchzuführen, als für jeden Vorgang eine separate Instanz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="47599-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="47599-107">Wenn Sie mehrere Massenkopiervorgänge mithilfe desselben <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts durchführen, bestehen keine Einschränkungen, ob sich die Quell- oder Zielinformationen bei jedem Vorgang gleichen oder unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="47599-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="47599-108">Sie müssen sich jedoch vergewissern, dass die Informationen der Spaltenzuordnung immer ordnungsgemäß festgelegt sind, wenn Sie auf den Server schreiben.</span><span class="sxs-lookup"><span data-stu-id="47599-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="47599-109">Dieses Beispiel wird nur dann ausgeführt, wenn Sie die Arbeits Tabellen erstellt haben, wie unter [Beispiel für Massen Kopier](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)Vorgänge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47599-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="47599-110">Dieser Code wird bereitgestellt, um die Syntax nur für die Verwendung von **SqlBulkCopy** zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="47599-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="47599-111">Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.</span><span class="sxs-lookup"><span data-stu-id="47599-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="47599-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47599-112">See also</span></span>

- [<span data-ttu-id="47599-113">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="47599-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="47599-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="47599-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
