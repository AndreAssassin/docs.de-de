---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: cb2a172ac4e6a0ce4852f4c7cf7044583d9ab6c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077760"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="6a652-102">Kopieren von DataSet-Inhalten</span><span class="sxs-lookup"><span data-stu-id="6a652-102">Copying DataSet Contents</span></span>
<span data-ttu-id="6a652-103">Sie können eine Kopie erstellen eine <xref:System.Data.DataSet> , damit Sie ohne Auswirkungen auf die ursprünglichen Daten mit Daten arbeiten können, oder Arbeiten mit einer Teilmenge der Daten aus einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6a652-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="6a652-104">Beim Kopieren einer **DataSet**, können Sie:</span><span class="sxs-lookup"><span data-stu-id="6a652-104">When copying a **DataSet**, you can:</span></span>  
  
-   <span data-ttu-id="6a652-105">Erstellen Sie eine genaue Kopie der **DataSet**, einschließlich Schema, Daten, Informationen zum Zeilenstatus und Zeilenversionen.</span><span class="sxs-lookup"><span data-stu-id="6a652-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
-   <span data-ttu-id="6a652-106">Erstellen Sie eine **DataSet** , enthält das Schema einer vorhandenen **DataSet**, aber nur die Zeilen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a652-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="6a652-107">Sie können alle Zeilen zurückgeben, die geändert wurden, oder geben Sie einen bestimmten **DataRowState**.</span><span class="sxs-lookup"><span data-stu-id="6a652-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="6a652-108">Weitere Informationen zum Zeilenstatus finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6a652-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
-   <span data-ttu-id="6a652-109">Kopieren Sie das Schema oder die relationale Struktur von den **DataSet** , ohne dass alle Zeilen kopiert.</span><span class="sxs-lookup"><span data-stu-id="6a652-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="6a652-110">Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a652-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="6a652-111">Erstellen Sie eine genaue Kopie der **DataSet** , die sowohl Schema-als auch Daten enthält, verwenden Sie die <xref:System.Data.DataSet.Copy%2A> -Methode der der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6a652-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6a652-112">Im folgenden Codebeispiel wird veranschaulicht, wie erstellen Sie eine genaue Kopie der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6a652-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="6a652-113">Erstellen Sie eine Kopie des eine **DataSet** , umfasst, Schema und nur die Daten darstellt **Added**, **"geändert"**, oder **gelöschte** Zeilen: Verwenden Sie die <xref:System.Data.DataSet.GetChanges%2A> Methode der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6a652-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6a652-114">Können Sie auch **GetChanges** zurückzugebenden nur Zeilen mit einem bestimmten Zeilenstatus durch Übergeben einer **DataRowState** Wert beim Aufruf von **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="6a652-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="6a652-115">Im folgenden Codebeispiel wird veranschaulicht, wie zum Übergeben einer **DataRowState** beim Aufrufen von **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="6a652-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="6a652-116">Erstellen Sie eine Kopie einer **DataSet** , nur die Schemas enthält, verwenden Sie die <xref:System.Data.DataSet.Clone%2A> -Methode der der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="6a652-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6a652-117">Sie können auch vorhandene Zeilen hinzufügen, auf die geklonte **DataSet** mithilfe der **ImportRow** Methode der **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="6a652-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="6a652-118">**ImportRow** Daten, die Zeile (Zustand) und die Versionsinformationen für die Zeile auf die angegebene Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a652-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="6a652-119">Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="6a652-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="6a652-120">Das folgende Codebeispiel erstellt einen Klon des eine **DataSet** und fügt dann die Zeilen aus der ursprünglichen **DataSet** auf die **Kunden** -Tabelle in der **DataSet**  -Klon für Kunden, in denen die **CountryRegion** Spalte hat den Wert "Germany".</span><span class="sxs-lookup"><span data-stu-id="6a652-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a652-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a652-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="6a652-122">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="6a652-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="6a652-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="6a652-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
