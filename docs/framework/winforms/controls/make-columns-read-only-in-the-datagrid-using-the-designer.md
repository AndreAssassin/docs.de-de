---
title: 'Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 8639c1e6f4382c1f91ed2c777b1b0ff29c5a60a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113515"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="be62a-102">Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="be62a-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="be62a-103">Benutzer können in der Standardeinstellung ändern, Text und numerischen Daten angezeigt, in der Windows-Formularen <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be62a-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be62a-104">Wenn Sie möchten die Daten anzuzeigen, die für die Änderung nicht vorgesehen ist, müssen Sie die Spalten, mit den Daten schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="be62a-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="be62a-105">Informationen dazu, wie Sie das Steuerelement vollständig schreibgeschützt machen, finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement mithilfe des Designers](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="be62a-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="be62a-106">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="be62a-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="be62a-107">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="be62a-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be62a-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="be62a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="be62a-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="be62a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="be62a-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="be62a-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="be62a-111">Um eine Spalte schreibgeschützt machen, indem Sie mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="be62a-111">To make a column read-only by using the designer</span></span>  
  
1.  <span data-ttu-id="be62a-112">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be62a-112">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="be62a-113">Wählen Sie eine Spalte aus der **Selected Columns** Liste.</span><span class="sxs-lookup"><span data-stu-id="be62a-113">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="be62a-114">In der **Spalteneigenschaften** Raster legen die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="be62a-114">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be62a-115">Sie können auch eine Spalte nur-Lese beim machen Sie es hinzufügen, indem Sie die Auswahl der **Read Only** Kontrollkästchen in der **Spalte hinzufügen** im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="be62a-115">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be62a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be62a-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="be62a-117">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="be62a-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="be62a-118">Vorgehensweise: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="be62a-118">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="be62a-119">Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="be62a-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="be62a-120">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be62a-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
