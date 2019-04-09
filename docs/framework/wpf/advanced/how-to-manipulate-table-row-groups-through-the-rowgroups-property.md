---
title: 'Vorgehensweise: Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: edc5fbe552a04387fc3f152cb53444605d142624
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209969"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="da034-102">Vorgehensweise: Bearbeiten der Zeilengruppen einer Tabelle mit der RowGroups-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="da034-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="da034-103">Dieses Beispiel veranschaulicht einige der häufigsten Vorgänge, die für eine Tabelle Zeilengruppen mit der ausgeführt werden können die <xref:System.Windows.Documents.Table.RowGroups%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="da034-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da034-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-104">Example</span></span>  
 <span data-ttu-id="da034-105">Im folgenden Beispiel wird eine neue Tabelle erstellt und verwendet dann die <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> Methode, um die Spalten der Tabelle hinzufügen <xref:System.Windows.Documents.Table.RowGroups%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="da034-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="da034-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-106">Example</span></span>  
 <span data-ttu-id="da034-107">Das folgende Beispiel fügt eine neue <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="da034-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="da034-108">Die neue Spalte wird eingefügt, an Indexposition 0 (null) erleichtert die neue Zeile für die erste Gruppe, in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="da034-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da034-109">Die <xref:System.Windows.Documents.TableRowGroupCollection> Auflistung standardmäßige nullbasierte Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="da034-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="da034-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-110">Example</span></span>  
 <span data-ttu-id="da034-111">Das folgende Beispiel fügt mehrere Zeilen mit einem bestimmten <xref:System.Windows.Documents.TableRowGroup> (angegeben durch den Index) in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="da034-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="da034-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-112">Example</span></span>  
 <span data-ttu-id="da034-113">Das folgende Beispiel greift auf eine beliebigen Eigenschaften in Zeilen in der ersten Zeilengruppe in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="da034-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="da034-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-114">Example</span></span>  
 <span data-ttu-id="da034-115">Das folgende Beispiel fügt mehrere Zellen auf einen bestimmten <xref:System.Windows.Documents.TableRow> (angegeben durch den Index) in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="da034-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="da034-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-116">Example</span></span>  
 <span data-ttu-id="da034-117">Im folgenden Beispiel wird Zugriff auf einige beliebige Methoden und Eigenschaften für Zellen in der ersten Zeile in der ersten Zeilengruppe.</span><span class="sxs-lookup"><span data-stu-id="da034-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="da034-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-118">Example</span></span>  
 <span data-ttu-id="da034-119">Das folgende Beispiel gibt die Anzahl der <xref:System.Windows.Documents.TableRowGroup> Elemente, die von der Tabelle gehostet.</span><span class="sxs-lookup"><span data-stu-id="da034-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="da034-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-120">Example</span></span>  
 <span data-ttu-id="da034-121">Im folgende Beispiel wird eine bestimmte Zeilengruppe entfernt, als Verweis.</span><span class="sxs-lookup"><span data-stu-id="da034-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="da034-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-122">Example</span></span>  
 <span data-ttu-id="da034-123">Im folgende Beispiel wird eine bestimmte Zeilengruppe nach Index entfernt.</span><span class="sxs-lookup"><span data-stu-id="da034-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="da034-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da034-124">Example</span></span>  
 <span data-ttu-id="da034-125">Im folgende Beispiel entfernt alle Zeilengruppen aus der Tabelle Zeile Groups-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="da034-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="da034-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da034-126">See also</span></span>

- [<span data-ttu-id="da034-127">Vorgehensweise: Bearbeiten von fortlaufenden Inhaltselementen mit der Inlines-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="da034-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="da034-128">Bearbeiten von einem FlowDocument mit der Blocks-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="da034-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="da034-129">Bearbeiten der Spalten einer Tabelle mit der Columns-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="da034-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
