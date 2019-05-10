---
title: 'Vorgehensweise: Verankern von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211275"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="15dc8-102">Vorgehensweise: Verankern von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15dc8-102">How to: Anchor Controls on Windows Forms</span></span>

<span data-ttu-id="15dc8-103">Wenn Sie ein Formular entwerfen, das der Benutzer zur Laufzeit ändern kann, sollten die Steuerelemente im Formular ändern der Größe und ordnungsgemäß neu zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="15dc8-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="15dc8-104">Steuerelemente dynamisch mit dem Formular ändern möchten, können Sie die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="15dc8-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="15dc8-105">Die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft definiert eine Ankerposition, die für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="15dc8-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="15dc8-106">Wenn ein Steuerelement zu einem Formular verankert ist, und des Formulars geändert wird, behält das Steuerelement den Abstand zwischen dem Steuerelement und das Anchorpositionen.</span><span class="sxs-lookup"><span data-stu-id="15dc8-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="15dc8-107">Angenommen, Sie haben eine <xref:System.Windows.Forms.TextBox> -Steuerelement, das auf der linken, rechten und unteren Rand des Formulars, verankert ist, wie des Formulars geändert wird, die <xref:System.Windows.Forms.TextBox> horizontal-Steuerelements geändert wird, sodass er die gleiche Distanz vom die Rechte und linke Seite des Formulars verwaltet.</span><span class="sxs-lookup"><span data-stu-id="15dc8-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="15dc8-108">Darüber hinaus wird das Steuerelement vertikal positioniert, sodass am Speicherort immer den gleichen Abstand vom unteren Rand des Formulars ist.</span><span class="sxs-lookup"><span data-stu-id="15dc8-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="15dc8-109">Wenn ein Steuerelement nicht verankert ist und die Größe des Formulars ist, wird die Position des Steuerelements relativ zu den Rändern des Formulars geändert.</span><span class="sxs-lookup"><span data-stu-id="15dc8-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="15dc8-110">Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="15dc8-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="15dc8-111">Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="15dc8-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="15dc8-112">Verankern eines Steuerelements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="15dc8-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="15dc8-113">Wählen Sie in Visual Studio das Steuerelement zu verankern.</span><span class="sxs-lookup"><span data-stu-id="15dc8-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15dc8-114">Sie können mehrere Steuerelemente gleichzeitig durch Drücken der STRG-Taste, auf jedes Steuerelement, um ihn auszuwählen und dann folgen den Rest dieses Verfahrens verankern.</span><span class="sxs-lookup"><span data-stu-id="15dc8-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="15dc8-115">In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="15dc8-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="15dc8-116">Ein Editor wird mit einem Kreuz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15dc8-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="15dc8-117">Um einen Anker festzulegen, klicken Sie auf die oberen, linken, rechten oder unteren Teil der Cross.</span><span class="sxs-lookup"><span data-stu-id="15dc8-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="15dc8-118">Steuerelemente sind oben verankert und wird standardmäßig links.</span><span class="sxs-lookup"><span data-stu-id="15dc8-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="15dc8-119">Um eine Seite des Steuerelements zu löschen, die verankert ist, klicken Sie auf diese Arm, der die kreuzfilterrichtung.</span><span class="sxs-lookup"><span data-stu-id="15dc8-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="15dc8-120">Schließen der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaften-Editor, klicken Sie auf die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaftennamen erneut.</span><span class="sxs-lookup"><span data-stu-id="15dc8-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="15dc8-121">Wenn das Formular zur Laufzeit angezeigt wird, wird die Größe des Steuerelements die gleiche Distanz vom Rand des Formulars positioniert bleiben.</span><span class="sxs-lookup"><span data-stu-id="15dc8-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="15dc8-122">Der Abstand zwischen dem verankerten Rand bleibt unverändert immer, wie der Abstand definiert, wenn das Steuerelement im Windows Forms-Designer befindet.</span><span class="sxs-lookup"><span data-stu-id="15dc8-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="15dc8-123">Bestimmte Steuerelemente, z. B. die <xref:System.Windows.Forms.ComboBox> steuern, besteht ein Limit, deren Größe.</span><span class="sxs-lookup"><span data-stu-id="15dc8-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="15dc8-124">Verankerung des Steuerelements am unteren Rand der Form oder den Container kann nicht erzwingen, dass das Steuerelement seine Höhe Grenzwert überschritten.</span><span class="sxs-lookup"><span data-stu-id="15dc8-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="15dc8-125">Geerbte Steuerelemente muss `Protected` verankert werden können.</span><span class="sxs-lookup"><span data-stu-id="15dc8-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="15dc8-126">Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen `Modifiers` -Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="15dc8-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="15dc8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15dc8-127">See also</span></span>

- [<span data-ttu-id="15dc8-128">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="15dc8-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="15dc8-129">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15dc8-129">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="15dc8-130">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="15dc8-130">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="15dc8-131">Vorgehensweise: Andocken von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15dc8-131">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="15dc8-132">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="15dc8-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="15dc8-133">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="15dc8-133">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="15dc8-134">Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="15dc8-134">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
