---
title: Übersicht über das StatusStrip-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: f6f2d4b19b7ec91c964c72e3aca85e0253c7cc22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129713"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="bdbbe-102">Übersicht über das StatusStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bdbbe-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="bdbbe-103">Ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement zeigt Informationen zu einem Objekt an, das in einem <xref:System.Windows.Forms.Form> angezeigt wird, zu den Komponenten des Objekts oder Kontextinformationen, die sich auf die Operation dieses Objekts in Ihrer Anwendung beziehen.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="bdbbe-104">Ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement besteht normalerweise aus <xref:System.Windows.Forms.ToolStripStatusLabel>-Objekten, von denen jedes Text, ein Symbol oder beides anzeigt.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="bdbbe-105">Der <xref:System.Windows.Forms.StatusStrip> kann zudem auch <xref:System.Windows.Forms.ToolStripDropDownButton>-, <xref:System.Windows.Forms.ToolStripSplitButton> und <xref:System.Windows.Forms.ToolStripProgressBar>-Steuerelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="bdbbe-106">Der standardmäßige <xref:System.Windows.Forms.StatusStrip> weist keine Panels auf.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="bdbbe-107">Verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>-Methode, um einem <xref:System.Windows.Forms.StatusStrip> Panels hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="bdbbe-108">Es gibt umfassende Unterstützung für den Umgang mit <xref:System.Windows.Forms.StatusStrip>-Elementen und häufig verwendeten Befehle in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="bdbbe-109">Siehe auch [StatusStrip-Elementauflistungs-Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) und [StatusStrip-Aufgaben (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bdbbe-109">Also see [StatusStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) and [StatusStrip Tasks Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span></span>  
  
 <span data-ttu-id="bdbbe-110">Obwohl <xref:System.Windows.Forms.StatusStrip> das <xref:System.Windows.Forms.StatusBar>-Steuerelement vorheriger Versionen ersetzt und erweitert, wird das <xref:System.Windows.Forms.StatusBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="bdbbe-111">Wichtige StatusStrip-Member</span><span class="sxs-lookup"><span data-stu-id="bdbbe-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="bdbbe-112">Name</span><span class="sxs-lookup"><span data-stu-id="bdbbe-112">Name</span></span>|<span data-ttu-id="bdbbe-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdbbe-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="bdbbe-114">Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.StatusStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="bdbbe-115">Ruft einen Wert ab, der angibt, ob sich das <xref:System.Windows.Forms.StatusStrip>-Objekt in seinem <xref:System.Windows.Forms.ToolStripContainer>-Objekt von einem Ende zum anderen Ende erstreckt, oder legt diesen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="bdbbe-116">Wichtige StatusStrip-Begleitklassen</span><span class="sxs-lookup"><span data-stu-id="bdbbe-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="bdbbe-117">Name</span><span class="sxs-lookup"><span data-stu-id="bdbbe-117">Name</span></span>|<span data-ttu-id="bdbbe-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdbbe-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="bdbbe-119">Stellt ein Panel in einem <xref:System.Windows.Forms.StatusStrip>-Steuerelement dar.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="bdbbe-120">Zeigt eine zugehörige <xref:System.Windows.Forms.ToolStripDropDown> an, aus der der Benutzer ein einzelnes Element auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="bdbbe-121">Stellt ein zweiteiliges Steuerelement dar, das aus einer Standardschaltfläche und einem Dropdownmenü besteht.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="bdbbe-122">Zeigt den Fortschrittsstatus eines Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="bdbbe-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdbbe-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdbbe-123">See also</span></span>

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
