---
title: 'Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 40fccee551e7840ef474e7775873d4e7178748fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194317"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c816d-102">Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c816d-102">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c816d-103">Manchmal möchten Sie nur einige der Spalten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c816d-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c816d-104">Benutzern, die sich mit Anmeldeinformationen der Geschäftsleitung anmelden, möchten Sie beispielsweise eine Spalte mit den Gehältern der Angestellten anzeigen, diese aber für andere Benutzer ausblenden.</span><span class="sxs-lookup"><span data-stu-id="c816d-104">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="c816d-105">Oder aber Sie möchten das Steuerelement an eine Datenquelle binden, die viele Spalten enthält, von denen Sie nur einige anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="c816d-105">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="c816d-106">In diesem Fall entfernen Sie in der Regel die Spalten, deren Anzeige Sie nicht interessiert, anstatt sie auszublenden.</span><span class="sxs-lookup"><span data-stu-id="c816d-106">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="c816d-107">Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>-Eigenschaftswert einer Spalte, ob diese Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c816d-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="c816d-108">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="c816d-108">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="c816d-109">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Ausblenden von Spalten in der Windows Forms-DataGridView-Steuerelement mithilfe des Designers](hide-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c816d-109">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="c816d-110">So blenden Sie eine Spalte programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="c816d-110">To hide a column programmatically</span></span>  
  
-   <span data-ttu-id="c816d-111">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> -Eigenschaft auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="c816d-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="c816d-112">Wenn Sie eine während der Datenbindung automatisch generierte `CustomerID`-Spalte ausblenden möchten, platzieren Sie das folgende Codebeispiel in einem <xref:System.Windows.Forms.DataGridView.DataBindingComplete>-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c816d-112">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c816d-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c816d-113">Compiling the Code</span></span>  
 <span data-ttu-id="c816d-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c816d-114">This example requires:</span></span>  
  
-   <span data-ttu-id="c816d-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `CustomerID` enthält.</span><span class="sxs-lookup"><span data-stu-id="c816d-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
-   <span data-ttu-id="c816d-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c816d-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c816d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c816d-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c816d-118">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c816d-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="c816d-119">Vorgehensweise: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c816d-119">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="c816d-120">Vorgehensweise: Ändern Sie die Reihenfolge der Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c816d-120">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)
