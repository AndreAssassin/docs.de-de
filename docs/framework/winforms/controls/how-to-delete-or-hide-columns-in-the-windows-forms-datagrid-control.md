---
title: 'Vorgehensweise: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 70229abddb831788f521f85747db1093c941ba8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967372"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="2b43e-102">Vorgehensweise: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b43e-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="2b43e-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2b43e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2b43e-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2b43e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="2b43e-105">Sie können <xref:System.Windows.Forms.DataGrid> Spalten im Windows Forms Steuerelement Programm gesteuert löschen oder ausblenden, indem Sie die Eigenschaften und Methoden <xref:System.Windows.Forms.GridColumnStylesCollection> des-Objekts und des-Objekts (die <xref:System.Windows.Forms.DataGridTableStyle> Member der- <xref:System.Windows.Forms.DataGridColumnStyle> Klasse sind) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b43e-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="2b43e-106">Die gelöschten oder ausgeblendeten Spalten sind immer noch in der Datenquelle vorhanden, an die das Raster gebunden ist, und es kann weiterhin Programm gesteuert darauf zugegriffen werden</span><span class="sxs-lookup"><span data-stu-id="2b43e-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="2b43e-107">Sie sind nicht mehr im DataGrid sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2b43e-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b43e-108">Wenn Ihre Anwendung nicht auf bestimmte Datenspalten zugreift, und Sie nicht möchten, dass Sie im DataGrid angezeigt werden, ist es wahrscheinlich nicht notwendig, Sie zuerst in die Datenquelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="2b43e-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="2b43e-109">So löschen Sie eine Spalte Programm gesteuert aus dem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2b43e-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="2b43e-110">Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="2b43e-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="2b43e-111">Legen Sie <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> die-Eigenschaft auf die Tabelle in der Datenquelle fest, auf die der Stil angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b43e-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="2b43e-112">Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft verwendet, von der angenommen wird, dass bereits festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2b43e-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="2b43e-113">Fügen Sie das <xref:System.Windows.Forms.DataGridTableStyle> neue-Objekt zur Auflistung der Tabellen Stile des DataGrid hinzu.</span><span class="sxs-lookup"><span data-stu-id="2b43e-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="2b43e-114">Ruft die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> <xref:System.Windows.Forms.DataGrid>-Methode der- <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Auflistung auf und gibt den Spalten Index der zu löschenden Spalte an.</span><span class="sxs-lookup"><span data-stu-id="2b43e-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="2b43e-115">So blenden Sie eine Spalte im DataGrid Programm gesteuert aus</span><span class="sxs-lookup"><span data-stu-id="2b43e-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="2b43e-116">Deklarieren Sie im Deklarations Bereich Ihres Formulars eine neue Instanz der <xref:System.Windows.Forms.DataGridTableStyle> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="2b43e-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="2b43e-117">Legen Sie <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> die-Eigenschaft <xref:System.Windows.Forms.DataGridTableStyle> des-Objekts auf die Tabelle in der Datenquelle fest, auf die Sie den Stil anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2b43e-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="2b43e-118">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft verwendet, von der angenommen wird, dass bereits festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2b43e-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="2b43e-119">Fügen Sie das <xref:System.Windows.Forms.DataGridTableStyle> neue-Objekt zur Auflistung der Tabellen Stile des DataGrid hinzu.</span><span class="sxs-lookup"><span data-stu-id="2b43e-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="2b43e-120">Blenden Sie die Spalte durch Festlegen `Width` der-Eigenschaft auf 0 aus, und geben Sie dabei den Spalten Index der auszublendenden Spalte an.</span><span class="sxs-lookup"><span data-stu-id="2b43e-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2b43e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b43e-121">See also</span></span>

- [<span data-ttu-id="2b43e-122">Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit im DataGrid-Steuerelement Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b43e-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="2b43e-123">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2b43e-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
