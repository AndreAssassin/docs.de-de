---
title: DataView-Leistung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: f0a85232b753eed891cded4b0fb1154269b30dc9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606943"
---
# <a name="dataview-performance"></a><span data-ttu-id="2219f-102">DataView-Leistung</span><span class="sxs-lookup"><span data-stu-id="2219f-102">DataView Performance</span></span>
<span data-ttu-id="2219f-103">In diesem Thema wird beschrieben, wie sich die Verwendung der Methoden <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> der <xref:System.Data.DataView>-Klasse und die Zwischenspeicherung einer <xref:System.Data.DataView> in einer Webanwendung positiv auf die Arbeitsgeschwindigkeit auswirken können.</span><span class="sxs-lookup"><span data-stu-id="2219f-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="2219f-104">"Find" und "FindRows"</span><span class="sxs-lookup"><span data-stu-id="2219f-104">Find and FindRows</span></span>  
 <span data-ttu-id="2219f-105"><xref:System.Data.DataView> generiert einen Index.</span><span class="sxs-lookup"><span data-stu-id="2219f-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="2219f-106">Ein Index enthält Schlüssel, die auf der Grundlage einer oder mehrerer Spalten in der Tabelle oder Ansicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2219f-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="2219f-107">Diese Schlüssel werden in einer Struktur gespeichert, mit der die <xref:System.Data.DataView> schnell und effizient die Zeile(n) finden kann, die mit den Schlüsselwerten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2219f-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="2219f-108">Vorgänge, die den Index, wie beispielsweise Filterung und Sortierung verwenden, finden Sie unter erhebliche Leistungssteigerungen.</span><span class="sxs-lookup"><span data-stu-id="2219f-108">Operations that use the index, such as filtering and sorting, see significant performance increases.</span></span> <span data-ttu-id="2219f-109">Der Index für eine <xref:System.Data.DataView> wird sowohl dann generiert, wenn die <xref:System.Data.DataView> erstellt wird, als auch dann, wenn Änderungen an den Sortier- oder Filterinformationen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="2219f-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="2219f-110">Wenn Sie eine <xref:System.Data.DataView> erstellen, ohne gleich auch die Sortier- und Filterinformationen festzulegen, wird der Index mindestens zweimal generiert: das erste Mal, wenn die <xref:System.Data.DataView> erstellt wird, und das zweite Mal, sobald eine der Sortier- oder Filtereigenschaften geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2219f-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="2219f-111">Weitere Informationen zu filtern und Sortieren mit <xref:System.Data.DataView>, finden Sie unter [Filtern mit DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) und [Sortieren mit DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="2219f-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="2219f-112">Wenn Sie die Ergebnisse einer bestimmten Abfrage von Daten zurückgeben möchten, anstatt eine dynamische Ansicht einer Teilmenge von Daten zu erhalten, können Sie die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> der <xref:System.Data.DataView> verwenden, statt die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft einzurichten.</span><span class="sxs-lookup"><span data-stu-id="2219f-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="2219f-113">Die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft wird am besten in einer datengebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2219f-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="2219f-114">Wenn Sie die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Arbeitsgeschwindigkeit verringert wird.</span><span class="sxs-lookup"><span data-stu-id="2219f-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="2219f-115">Die Methoden <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="2219f-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="2219f-116">Wenn Sie <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> nur einmal aufrufen werden, sollten Sie die vorhandene <xref:System.Data.DataView> verwenden.</span><span class="sxs-lookup"><span data-stu-id="2219f-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="2219f-117">Wird <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> dagegen mehrmals aufgerufen, empfiehlt sich die Erstellung einer neuen <xref:System.Data.DataView>, um den Index auf der Basis der zu durchsuchenden Spalte neu zu erstellen, und dann die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2219f-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="2219f-118">Weitere Informationen zu den <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> Methoden finden Sie unter [Suchen nach Zeilen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="2219f-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="2219f-119">Im folgenden Beispiel wird die <xref:System.Data.DataView.Find%2A>-Methode verwendet, um einen Kontakt mit dem Nachnamen "Zhu" zu finden.</span><span class="sxs-lookup"><span data-stu-id="2219f-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="2219f-120">Im folgenden Beispiel wird die <xref:System.Data.DataView.FindRows%2A>-Methode verwendet, um alle Produkte mit roter Farbe abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2219f-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="2219f-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2219f-121">ASP.NET</span></span>  
 <span data-ttu-id="2219f-122">ASP.NET verfügt über einen Cachemechanismus zur Zwischenspeicherung von Objekten, die die Serverressourcen in starkem Maße beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="2219f-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="2219f-123">Durch die Zwischenspeicherung dieser Ressourcen kann die Geschwindigkeit Ihrer Anwendung wesentlich verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="2219f-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="2219f-124">Die Zwischenspeicherung wird von der Klasse <xref:System.Web.Caching.Cache> implementiert. Die dabei zum Einsatz kommenden Cacheinstanzen sind jeweils anwendungsspezifisch und privat.</span><span class="sxs-lookup"><span data-stu-id="2219f-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="2219f-125">Da das Erstellen eines neuen <xref:System.Data.DataView>-Objekts die Ressourcen stark beanspruchen kann, kann mit der Zwischenspeicherfunktionalität in Webanwendungen verhindert werden, dass die <xref:System.Data.DataView> bei jeder Aktualisierung der Webseite neu erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="2219f-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="2219f-126">Im folgenden Beispiel wird die <xref:System.Data.DataView> im Cache zwischengespeichert. So wird dafür gesorgt, dass die Daten nicht neu sortiert werden müssen, wenn die Seite aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2219f-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.                  
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="2219f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2219f-127">See also</span></span>

- [<span data-ttu-id="2219f-128">Datenbindung und LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2219f-128">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
