---
title: 'Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b4957a3f2efcb31594806a188e3d3bb10c2dac09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296393"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="7759d-102">Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular</span><span class="sxs-lookup"><span data-stu-id="7759d-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="7759d-103">Mit dem <xref:System.Windows.Forms.MenuStrip>-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7759d-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="7759d-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit einem <xref:System.Windows.Forms.MenuStrip> Steuerelement an ein Standardmenü zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7759d-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="7759d-105">Das Formular reagiert auch auf, wenn ein Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="7759d-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="7759d-106">Die folgenden Aufgaben werden in dieser exemplarischen Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7759d-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="7759d-107">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="7759d-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="7759d-108">Erstellen ein Standardmenü.</span><span class="sxs-lookup"><span data-stu-id="7759d-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="7759d-109">Erstellen einer <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7759d-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="7759d-110">Behandeln von Menüauswahl-Element.</span><span class="sxs-lookup"><span data-stu-id="7759d-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="7759d-111">Wenn Sie fertig sind, haben Sie ein Formular mit Standardmenü, die die Auswahl von Menüelementen in zeigt eine <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7759d-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="7759d-112">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="7759d-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7759d-113">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="7759d-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7759d-114">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7759d-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7759d-115">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7759d-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7759d-116">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7759d-116">Prerequisites</span></span>  
 <span data-ttu-id="7759d-117">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7759d-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="7759d-118">Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7759d-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="7759d-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="7759d-119">Creating the Project</span></span>  
 <span data-ttu-id="7759d-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7759d-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="7759d-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="7759d-121">To create the project</span></span>  
  
1. <span data-ttu-id="7759d-122">Erstellen Sie ein Windows-Anwendungsprojekt namens **StandardMenuForm** (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="7759d-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="7759d-123">Wählen Sie im Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="7759d-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="7759d-124">Erstellen ein Standardmenü</span><span class="sxs-lookup"><span data-stu-id="7759d-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="7759d-125">Der Windows Forms-Designer können automatisch Auffüllen einer <xref:System.Windows.Forms.MenuStrip> -Steuerelement mit Standardmenüelementen.</span><span class="sxs-lookup"><span data-stu-id="7759d-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="7759d-126">So erstellen Sie ein Standardmenü</span><span class="sxs-lookup"><span data-stu-id="7759d-126">To create a standard menu</span></span>  
  
1. <span data-ttu-id="7759d-127">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.MenuStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="7759d-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2. <span data-ttu-id="7759d-128">Klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> des Steuerelements Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie **Standardelemente einfügen**.</span><span class="sxs-lookup"><span data-stu-id="7759d-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="7759d-129">Die <xref:System.Windows.Forms.MenuStrip> Steuerelement mit Standardmenüelemente gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="7759d-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3. <span data-ttu-id="7759d-130">Klicken Sie auf die **Datei** Menüelement, um die Standard-Menüelemente und entsprechende Symbole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7759d-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="7759d-131">Erstellen eine StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7759d-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="7759d-132">Verwenden der <xref:System.Windows.Forms.StatusStrip> -Steuerelement zum Anzeigen des Status Ihrer Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7759d-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="7759d-133">Im aktuellen Beispiel-Menüelemente, die vom Benutzer ausgewählten werden angezeigt, einem <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7759d-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="7759d-134">So erstellen Sie eine StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7759d-134">To create a StatusStrip control</span></span>  
  
1. <span data-ttu-id="7759d-135">Von der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.StatusStrip> Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="7759d-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="7759d-136">Die <xref:System.Windows.Forms.StatusStrip> Steuerelement wird automatisch am unteren Rand des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="7759d-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2. <span data-ttu-id="7759d-137">Klicken Sie auf die <xref:System.Windows.Forms.StatusStrip> Dropdown-Schaltfläche des Steuerelements, und wählen **StatusLabel** Hinzufügen einer <xref:System.Windows.Forms.ToolStripStatusLabel> die Steuerung an die <xref:System.Windows.Forms.StatusStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7759d-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="7759d-138">Behandlung von Elementauswahl</span><span class="sxs-lookup"><span data-stu-id="7759d-138">Handling Item Selection</span></span>  
 <span data-ttu-id="7759d-139">Behandeln der <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis reagieren, wenn der Benutzer ein Menüelement auswählt.</span><span class="sxs-lookup"><span data-stu-id="7759d-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="7759d-140">Behandeln von Elementauswahl</span><span class="sxs-lookup"><span data-stu-id="7759d-140">To handle item selection</span></span>  
  
1. <span data-ttu-id="7759d-141">Klicken Sie auf die **Datei** Menüelement, das Sie in der erstellen erstellt ein Standardmenü-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="7759d-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2. <span data-ttu-id="7759d-142">Klicken Sie im Fenster **Eigenschaften** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="7759d-142">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="7759d-143">Doppelklicken Sie auf die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7759d-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="7759d-144">Der Windows Forms-Designer wird ein Ereignishandler für die <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7759d-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4. <span data-ttu-id="7759d-145">Fügen Sie den folgenden Code in den Ereignishandler an.</span><span class="sxs-lookup"><span data-stu-id="7759d-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5. <span data-ttu-id="7759d-146">Fügen Sie der `UpdateStatus` Definition des Hilfsprogramm-Methode in das Formular.</span><span class="sxs-lookup"><span data-stu-id="7759d-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="7759d-147">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="7759d-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="7759d-148">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="7759d-148">To test your form</span></span>  
  
1. <span data-ttu-id="7759d-149">Drücken Sie F5, um Sie zu kompilieren und führen das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="7759d-149">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="7759d-150">Klicken Sie auf die **Datei** Menüelement, um das Menü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7759d-150">Click the **File** menu item to open the menu.</span></span>  
  
3. <span data-ttu-id="7759d-151">Auf der **Datei** Menü klicken Sie auf eines der Elemente, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7759d-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="7759d-152">Die <xref:System.Windows.Forms.StatusStrip> Steuerelement zeigt das ausgewählte Element.</span><span class="sxs-lookup"><span data-stu-id="7759d-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7759d-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7759d-153">Next Steps</span></span>  
 <span data-ttu-id="7759d-154">In dieser exemplarischen Vorgehensweise haben Sie ein Formular mit Standardmenü erstellt.</span><span class="sxs-lookup"><span data-stu-id="7759d-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="7759d-155">Sie können die <xref:System.Windows.Forms.ToolStrip> -Steuerelementfamilie zu vielen anderen Zwecken:</span><span class="sxs-lookup"><span data-stu-id="7759d-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="7759d-156">Erstellen von Kontextmenüs für Ihre Steuerelemente mit <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7759d-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="7759d-157">Weitere Informationen finden Sie unter [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7759d-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="7759d-158">Erstellen Sie ein Formular für multiple Document Interface (MDI) mit andockbaren <xref:System.Windows.Forms.ToolStrip> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="7759d-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="7759d-159">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines MDI-Formulars mit das Zusammenführen von Menüs und ToolStrip-Steuerelemente](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7759d-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="7759d-160">Geben Sie Ihre <xref:System.Windows.Forms.ToolStrip> steuert, ein professionelles Aussehen.</span><span class="sxs-lookup"><span data-stu-id="7759d-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="7759d-161">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="7759d-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7759d-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7759d-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="7759d-163">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7759d-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
