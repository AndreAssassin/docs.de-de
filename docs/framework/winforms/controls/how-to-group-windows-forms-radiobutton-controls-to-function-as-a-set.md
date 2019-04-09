---
title: 'Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c785b124d0b9efdbd9a1fa85819031cad3c8857c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117896"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="fcc08-102">Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set</span><span class="sxs-lookup"><span data-stu-id="fcc08-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="fcc08-103">Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente Benutzern eine Auswahl aus zwei oder mehr Einstellungen geben die nur eine an eine Prozedur oder dem Objekt zugewiesen werden kann sollen.</span><span class="sxs-lookup"><span data-stu-id="fcc08-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="fcc08-104">Z. B. eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente können eine Auswahl von Transportunternehmen für einen Auftrag anzeigen, aber nur ein Unternehmen ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fcc08-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="fcc08-105">Aus diesem Grund nur eine <xref:System.Windows.Forms.RadioButton> zu einem Zeitpunkt kann ausgewählt werden, auch wenn es sich um einen Teil einer funktionalen Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="fcc08-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="fcc08-106">Gruppieren, Optionsfelder werden in einem Container z. B. eine <xref:System.Windows.Forms.Panel> -Steuerelement, ein <xref:System.Windows.Forms.GroupBox> Steuerelement oder Formular.</span><span class="sxs-lookup"><span data-stu-id="fcc08-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="fcc08-107">Alle Optionsfelder, die direkt zu einer Form werden einer Gruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fcc08-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="fcc08-108">Um separate Gruppen hinzuzufügen, müssen Sie sie innerhalb von Bereichen oder Gruppenfelder platzieren.</span><span class="sxs-lookup"><span data-stu-id="fcc08-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="fcc08-109">Weitere Informationen zu Bereichen oder Gruppenfelder, finden Sie unter [Übersicht über Panel-Steuerelement](panel-control-overview-windows-forms.md) oder [Übersicht über das GroupBox-Steuerelement](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fcc08-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="fcc08-110">Zum Gruppieren von RadioButton-Steuerelementen als Gruppe unabhängig von anderen-Funktion</span><span class="sxs-lookup"><span data-stu-id="fcc08-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="fcc08-111">Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte die **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="fcc08-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="fcc08-112">Zeichnen Sie <xref:System.Windows.Forms.RadioButton> steuert, auf die <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fcc08-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc08-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcc08-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="fcc08-114">Übersicht über das RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fcc08-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="fcc08-115">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fcc08-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="fcc08-116">Übersicht über das GroupBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fcc08-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="fcc08-117">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fcc08-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="fcc08-118">RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fcc08-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
