---
title: 'Vorgehensweise: Einfügen von Zeilen in die Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: cb2319d51e0518114a04eea2fc7ab6b5a836b7ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328594"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="fd55e-102">Vorgehensweise: Einfügen von Zeilen in die Datenbank</span><span class="sxs-lookup"><span data-stu-id="fd55e-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="fd55e-103">Einfügen von Zeilen in einer Datenbank durch Hinzufügen von Objekten an die zugeordnete [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> Sammlung und übermitteln Sie dann die Änderungen an der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="fd55e-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="fd55e-104">übersetzt Ihre Änderungen in die entsprechenden SQL `INSERT` Befehle.</span><span class="sxs-lookup"><span data-stu-id="fd55e-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd55e-105">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="fd55e-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="fd55e-106">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="fd55e-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="fd55e-107">Können Entwickler mithilfe von Visual Studio die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.</span><span class="sxs-lookup"><span data-stu-id="fd55e-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="fd55e-108">In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.</span><span class="sxs-lookup"><span data-stu-id="fd55e-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="fd55e-109">Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Datenbankverbindung](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="fd55e-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="fd55e-110">So fügen Sie eine Zeile in die Datenbank ein</span><span class="sxs-lookup"><span data-stu-id="fd55e-110">To insert a row into the database</span></span>  
  
1. <span data-ttu-id="fd55e-111">Erstellen Sie ein neues Objekt, das die zu übermittelnden Spaltendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="fd55e-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2. <span data-ttu-id="fd55e-112">Fügen Sie das neue Objekt der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` Auflistung mit der Zieltabelle in der Datenbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd55e-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3. <span data-ttu-id="fd55e-113">Übergeben Sie die Änderung an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="fd55e-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd55e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd55e-114">Example</span></span>  
 <span data-ttu-id="fd55e-115">Im folgenden Codebeispiel wird ein neues Objekt des Typs `Order` erstellt und mit entsprechenden Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fd55e-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="fd55e-116">Anschließend wird das neue Objekt der `Order`-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fd55e-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="fd55e-117">Schließlich wird die Änderung an der Datenbank als neue Zeile in der `Orders`-Tabelle übergeben.</span><span class="sxs-lookup"><span data-stu-id="fd55e-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fd55e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd55e-118">See also</span></span>

- [<span data-ttu-id="fd55e-119">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="fd55e-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="fd55e-120">DataContext-Methoden (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="fd55e-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="fd55e-121">Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)</span><span class="sxs-lookup"><span data-stu-id="fd55e-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="fd55e-122">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="fd55e-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
