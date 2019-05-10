---
title: 'Vorgehensweise: Darstellen von Spalten als Klassenmember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 009da2579a6fe15cea3913ae5844fc886da2586c
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910745"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="cb81c-102">Vorgehensweise: Darstellen von Spalten als Klassenmember</span><span class="sxs-lookup"><span data-stu-id="cb81c-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="cb81c-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut einer Datenbankspalte ein Feld oder eine Eigenschaft zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cb81c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="cb81c-104">So ordnen Sie einer Datenbankspalte ein Feld oder eine Eigenschaft zu</span><span class="sxs-lookup"><span data-stu-id="cb81c-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="cb81c-105">Fügen Sie das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut der Eigenschaft oder Felddeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb81c-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb81c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb81c-106">Example</span></span>  
 <span data-ttu-id="cb81c-107">Der folgende Code weist das `CustomerID`-Feld in der `Customer`-Klasse der `CustomerID`-Spalte in der `Customers`-Datenbanktabelle zu.</span><span class="sxs-lookup"><span data-stu-id="cb81c-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="cb81c-108">Sie müssen die <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb81c-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="cb81c-109">Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.</span><span class="sxs-lookup"><span data-stu-id="cb81c-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb81c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb81c-110">See also</span></span>

- [<span data-ttu-id="cb81c-111">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="cb81c-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="cb81c-112">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="cb81c-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
