---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 31c597a0e2cbf41484f19c8d4179823e9fb929ba
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317674"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="89ed8-102">Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="89ed8-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="89ed8-103">Ausblenden von Menüelementen ist eine Möglichkeit, die Benutzeroberfläche (UI) Ihrer Anwendung steuern und User-Befehle zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="89ed8-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="89ed8-104">Häufig möchten ein ganzes Menü ausblenden, wenn alle Menüelemente im auf nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="89ed8-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="89ed8-105">Dies führt zu weniger ablenkungen für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="89ed8-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="89ed8-106">Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren Sie das Menü oder Menüelement, da allein durch das Ausblenden den Benutzer den Zugriff auf einen Menübefehl mit einer Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="89ed8-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="89ed8-107">Weitere Informationen zum Deaktivieren von Menüelementen, finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers](how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="89ed8-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89ed8-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="89ed8-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="89ed8-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="89ed8-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="89ed8-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="89ed8-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="89ed8-111">Um ein Menü der obersten Ebene und seine Untermenüelemente auszublenden.</span><span class="sxs-lookup"><span data-stu-id="89ed8-111">To hide a top-level menu and its submenu items</span></span>  
  
1. <span data-ttu-id="89ed8-112">Wählen Sie das Menüelement der obersten Ebene, und legen dessen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> oder <xref:System.Windows.Forms.ToolStripItem.Available%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="89ed8-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="89ed8-113">Wenn Sie das Menüelement der obersten Ebene ausblenden, werden auch alle Menüelemente in diesem Menü ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="89ed8-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="89ed8-114">Wenn Sie irgendwo anders als auf klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> nach dem Festlegen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> zu `false`, die gesamte Menüelement der obersten Ebene und seine Untermenüelemente, die aus dem Formular zeigt Ihnen daher die Auswirkungen der Laufzeit Ihrer Aktion ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="89ed8-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="89ed8-115">Um die ausgeblendeten Menüelement der obersten Ebene zur Entwurfszeit anzuzeigen, klicken Sie auf die <xref:System.Windows.Forms.MenuStrip> in die **Komponentenleiste**im **Dokumentgliederung**, bzw. im oberen Bereich des Eigenschaftenrasters.</span><span class="sxs-lookup"><span data-stu-id="89ed8-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89ed8-116">Sie werden nur selten ein ganzes Menü mit Ausnahme von mehrere untergeordnete Menüs mit Document Interface (MDI) in einem Szenario mit Zusammenführen ausblenden.</span><span class="sxs-lookup"><span data-stu-id="89ed8-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="89ed8-117">So blenden Sie ein Untermenüelement aus.</span><span class="sxs-lookup"><span data-stu-id="89ed8-117">To hide a submenu item</span></span>  
  
1. <span data-ttu-id="89ed8-118">Wählen Sie das Untermenüelement, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="89ed8-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="89ed8-119">Wenn Sie ein Untermenüelement ausblenden, bleibt es auf das Formular zur Entwurfszeit angezeigt, damit Sie es einfach für die weitere Bearbeitung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="89ed8-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="89ed8-120">Es werden tatsächlich zur Laufzeit ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="89ed8-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ed8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89ed8-121">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="89ed8-122">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="89ed8-122">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="89ed8-123">Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="89ed8-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
