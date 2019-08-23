---
title: 'Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: bac24c2dd622ea780408e902d08708ac09561044
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922722"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="6317c-102">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="6317c-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="6317c-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6317c-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6317c-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6317c-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="6317c-105">Das Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement wurde speziell zum Anzeigen von Informationen aus einer Datenquelle entwickelt.</span><span class="sxs-lookup"><span data-stu-id="6317c-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="6317c-106">Sie binden das Steuerelement zur Laufzeit, indem Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6317c-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="6317c-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, handelt es sich bei den meisten Quellen um Datasets und Datenansichten.</span><span class="sxs-lookup"><span data-stu-id="6317c-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="6317c-108">So binden Sie das DataGrid-Steuerelement Programm gesteuert ein</span><span class="sxs-lookup"><span data-stu-id="6317c-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="6317c-109">Schreiben Sie Code, um das DataSet auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="6317c-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="6317c-110">Wenn es sich bei der Datenquelle um ein DataSet oder eine Datenansicht handelt, die auf einer Datasettabelle basiert, fügen Sie dem Formular Code hinzu, um das DataSet zu füllen.</span><span class="sxs-lookup"><span data-stu-id="6317c-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="6317c-111">Der genaue Code, den Sie verwenden, hängt davon ab, wo das DataSet Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="6317c-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="6317c-112">Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, wird in der Regel die `Fill` -Methode eines Daten Adapters aufgerufen, wie im folgenden Beispiel gezeigt, das ein DataSet mit dem `DsCategories1`Namen auffüllt:</span><span class="sxs-lookup"><span data-stu-id="6317c-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="6317c-113">Wenn das DataSet von einem XML-Webdienst ausgefüllt wird, erstellen Sie in der Regel eine Instanz des Diensts im Code und rufen dann eine seiner Methoden auf, um ein DataSet zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6317c-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="6317c-114">Anschließend führen Sie das DataSet aus dem XML-Webdienst in Ihr lokales DataSet zusammen.</span><span class="sxs-lookup"><span data-stu-id="6317c-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="6317c-115">Im folgenden Beispiel wird gezeigt, wie Sie eine Instanz eines XML-Webdiensts `CategoriesService`mit dem Namen `GetCategories` erstellen, seine-Methode aufrufen und das resultierende DataSet in einem lokalen `DsCategories1`DataSet mit dem Namen zusammenführen können:</span><span class="sxs-lookup"><span data-stu-id="6317c-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="6317c-116">Wenden Sie <xref:System.Windows.Forms.DataGrid> die- <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode des-Steuer Elements an, und übergeben Sie dabei die Datenquelle und einen Datenmember.</span><span class="sxs-lookup"><span data-stu-id="6317c-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="6317c-117">Wenn Sie einen Datenmember nicht explizit übergeben müssen, übergeben Sie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6317c-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6317c-118">Wenn Sie das Raster zum ersten Mal binden, können Sie die-Eigenschaft und <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft des-Steuer Elements festlegen.</span><span class="sxs-lookup"><span data-stu-id="6317c-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="6317c-119">Sie können diese Eigenschaften jedoch nicht zurücksetzen, sobald Sie festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="6317c-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="6317c-120">Daher wird empfohlen, immer die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6317c-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="6317c-121">Im folgenden Beispiel wird gezeigt, wie Sie Programm gesteuert an die Customers-Tabelle in einem DataSet `DsCustomers1`mit dem Namen binden können:</span><span class="sxs-lookup"><span data-stu-id="6317c-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="6317c-122">Wenn die Customers-Tabelle die einzige Tabelle im DataSet ist, können Sie das Raster wahlweise wie folgt binden:</span><span class="sxs-lookup"><span data-stu-id="6317c-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="6317c-123">Optionale Fügen Sie dem Raster die entsprechenden Tabellen Stile und Spalten Stile hinzu.</span><span class="sxs-lookup"><span data-stu-id="6317c-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="6317c-124">Wenn keine Tabellen Stile vorhanden sind, wird die Tabelle angezeigt, jedoch mit minimaler Formatierung und allen sichtbaren Spalten.</span><span class="sxs-lookup"><span data-stu-id="6317c-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6317c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6317c-125">See also</span></span>

- [<span data-ttu-id="6317c-126">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6317c-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="6317c-127">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6317c-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="6317c-128">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6317c-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="6317c-129">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6317c-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
