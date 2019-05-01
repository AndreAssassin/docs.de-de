---
title: RepeatButton-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053313"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="8c81e-102">RepeatButton-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8c81e-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="8c81e-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8c81e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="8c81e-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="8c81e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8c81e-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8c81e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="8c81e-106">RepeatButton-Teile</span><span class="sxs-lookup"><span data-stu-id="8c81e-106">RepeatButton Parts</span></span>

<span data-ttu-id="8c81e-107">Die <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="8c81e-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="8c81e-108">RepeatButton-Zustände</span><span class="sxs-lookup"><span data-stu-id="8c81e-108">RepeatButton States</span></span>

<span data-ttu-id="8c81e-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8c81e-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="8c81e-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="8c81e-110">VisualState Name</span></span>|<span data-ttu-id="8c81e-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="8c81e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8c81e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c81e-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="8c81e-113">Normal</span><span class="sxs-lookup"><span data-stu-id="8c81e-113">Normal</span></span>|<span data-ttu-id="8c81e-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-114">CommonStates</span></span>|<span data-ttu-id="8c81e-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="8c81e-115">The default state.</span></span>|
|<span data-ttu-id="8c81e-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8c81e-116">MouseOver</span></span>|<span data-ttu-id="8c81e-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-117">CommonStates</span></span>|<span data-ttu-id="8c81e-118">Der Mauszeiger ist über dem Steuerelement positioniert.</span><span class="sxs-lookup"><span data-stu-id="8c81e-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="8c81e-119">Gedrückt</span><span class="sxs-lookup"><span data-stu-id="8c81e-119">Pressed</span></span>|<span data-ttu-id="8c81e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-120">CommonStates</span></span>|<span data-ttu-id="8c81e-121">Das Steuerelement wird gedrückt.</span><span class="sxs-lookup"><span data-stu-id="8c81e-121">The control is pressed.</span></span>|
|<span data-ttu-id="8c81e-122">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="8c81e-122">Disabled</span></span>|<span data-ttu-id="8c81e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-123">CommonStates</span></span>|<span data-ttu-id="8c81e-124">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8c81e-124">The control is disabled.</span></span>|
|<span data-ttu-id="8c81e-125">Focused</span><span class="sxs-lookup"><span data-stu-id="8c81e-125">Focused</span></span>|<span data-ttu-id="8c81e-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-126">FocusStates</span></span>|<span data-ttu-id="8c81e-127">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8c81e-127">The control has focus.</span></span>|
|<span data-ttu-id="8c81e-128">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="8c81e-128">Unfocused</span></span>|<span data-ttu-id="8c81e-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-129">FocusStates</span></span>|<span data-ttu-id="8c81e-130">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8c81e-130">The control does not have focus.</span></span>|
|<span data-ttu-id="8c81e-131">Gültig</span><span class="sxs-lookup"><span data-stu-id="8c81e-131">Valid</span></span>|<span data-ttu-id="8c81e-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-132">ValidationStates</span></span>|<span data-ttu-id="8c81e-133">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="8c81e-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="8c81e-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8c81e-134">InvalidFocused</span></span>|<span data-ttu-id="8c81e-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-135">ValidationStates</span></span>|<span data-ttu-id="8c81e-136">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="8c81e-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="8c81e-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8c81e-137">InvalidUnfocused</span></span>|<span data-ttu-id="8c81e-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8c81e-138">ValidationStates</span></span>|<span data-ttu-id="8c81e-139">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="8c81e-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="8c81e-140">RepeatButton-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c81e-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="8c81e-141">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8c81e-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="8c81e-142">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c81e-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="8c81e-143">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8c81e-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c81e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c81e-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8c81e-145">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="8c81e-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8c81e-146">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="8c81e-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8c81e-147">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8c81e-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="8c81e-148">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8c81e-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
