---
title: 'Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 38a366003a856adaf0840d0d8911263bc40dfe23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151410"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="a53ec-102">Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="a53ec-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="a53ec-103">Können Sie einschränken oder erweitern die Befehle, die ein Benutzer aktivieren und Deaktivieren von Menüelementen in Benutzeraktivitäten herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a53ec-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="a53ec-104">Menüelemente sind standardmäßig aktiviert, wenn sie erstellt wurden, aber dies die angepasst werden kann, über die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a53ec-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="a53ec-105">Sie können diese Eigenschaft zur Entwurfszeit im Bearbeiten der **Eigenschaften** Fenster oder programmgesteuert, indem sie im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="a53ec-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="a53ec-106">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="a53ec-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a53ec-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a53ec-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a53ec-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a53ec-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a53ec-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a53ec-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="a53ec-110">So deaktivieren Sie ein Menüelement zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="a53ec-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="a53ec-111">Mit dem Menüelement, auf das Formular ausgewählt haben, legen Sie die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a53ec-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a53ec-112">Deaktivieren das erste oder der obersten Ebene Menüelement in einem Menü, deaktiviert alle Menüelemente im Menü enthalten.</span><span class="sxs-lookup"><span data-stu-id="a53ec-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="a53ec-113">Ebenso wird beim Deaktivieren eines Menüelements, das über Untermenüelemente verfügt die Untermenüelemente deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a53ec-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="a53ec-114">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, gilt die guten Programmierstil, ausgeblendet und deaktiviert das gesamte Menü, wie dies führt zu eine sauberen-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a53ec-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="a53ec-115">Sie sollten auch deaktivieren Sie im Menü wie ausblenden, die nur Zugriff auf einen Menübefehl über eine Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="a53ec-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="a53ec-116">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft eines Elements zum Menü der obersten Ebene `false` das gesamte Menü ausblenden.</span><span class="sxs-lookup"><span data-stu-id="a53ec-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53ec-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a53ec-117">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="a53ec-118">Vorgehensweise: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="a53ec-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="a53ec-119">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a53ec-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
