---
title: 'Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 233b17de17b7f50547b2f4fbf6a543d7258183cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517095"
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="83c1f-102">Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="83c1f-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="83c1f-103">ermöglicht es Ihnen, ein auf beliebigen Klassen basierendes Datenmodell zu definieren, solange die Klassen als Objekte verfügbar gemacht werden, die die <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="83c1f-103">enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="83c1f-104">Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="83c1f-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c1f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83c1f-105">Example</span></span>  
 <span data-ttu-id="83c1f-106">Im folgenden Beispiel wird ein Datenmodell definiert, das `Orders` und `Items` enthält.</span><span class="sxs-lookup"><span data-stu-id="83c1f-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="83c1f-107">Die Entitätscontainerklasse `OrderItemData` enthält zwei öffentliche Methoden, die <xref:System.Linq.IQueryable%601>-Schnittstellen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="83c1f-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="83c1f-108">Diese Schnittstellen sind die Entitätenmengen der Entitätstypen `Orders` und `Items`.</span><span class="sxs-lookup"><span data-stu-id="83c1f-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="83c1f-109">Eine `Order` kann mehrere `Items` enthalten, daher verfügt der `Orders`-Entitätstyp über eine `Items`-Navigationseigenschaft, die eine Auflistung von `Items`-Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="83c1f-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="83c1f-110">Die `OrderItemData`-Entitätscontainerklasse ist der generische Typ der <xref:System.Data.Services.DataService%601>-Klasse, von der der `OrderItems`-Datendienst abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="83c1f-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c1f-111">Da in diesem Beispiel ein Datenanbieter im Arbeitsspeicher veranschaulicht wird und Änderungen außerhalb der aktuellen Objektinstanzen nicht beibehalten werden, leitet sich aus der Implementierung der <xref:System.Data.Services.IUpdatable>-Schnittstelle kein Vorteil ab.</span><span class="sxs-lookup"><span data-stu-id="83c1f-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="83c1f-112">Ein Beispiel zur Implementierung der <xref:System.Data.Services.IUpdatable> Benutzeroberfläche, siehe [wie: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="83c1f-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_reflection_provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_reflection_provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="83c1f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83c1f-113">See also</span></span>

- [<span data-ttu-id="83c1f-114">Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="83c1f-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
- [<span data-ttu-id="83c1f-115">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="83c1f-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="83c1f-116">Vorgehensweise: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="83c1f-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
