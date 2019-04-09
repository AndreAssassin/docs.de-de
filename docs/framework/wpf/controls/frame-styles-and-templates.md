---
title: Frame-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 6b084cfa31efebe2456871a99cd810741aa26609
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131019"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="5f6e0-102">Frame-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5f6e0-102">Frame Styles and Templates</span></span>
<span data-ttu-id="5f6e0-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="5f6e0-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5f6e0-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="5f6e0-106">Frame-Teile</span><span class="sxs-lookup"><span data-stu-id="5f6e0-106">Frame Parts</span></span>  
 <span data-ttu-id="5f6e0-107">Die folgende Tabelle enthält die benannten Teile für den <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="5f6e0-108">Segment</span><span class="sxs-lookup"><span data-stu-id="5f6e0-108">Part</span></span>|<span data-ttu-id="5f6e0-109">Typ</span><span class="sxs-lookup"><span data-stu-id="5f6e0-109">Type</span></span>|<span data-ttu-id="5f6e0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f6e0-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5f6e0-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="5f6e0-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="5f6e0-112">Der Inhaltsbereich.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="5f6e0-113">Frame-Zustände</span><span class="sxs-lookup"><span data-stu-id="5f6e0-113">Frame States</span></span>  
 <span data-ttu-id="5f6e0-114">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="5f6e0-115">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="5f6e0-115">VisualState Name</span></span>|<span data-ttu-id="5f6e0-116">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="5f6e0-116">VisualStateGroup Name</span></span>|<span data-ttu-id="5f6e0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f6e0-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5f6e0-118">Gültig</span><span class="sxs-lookup"><span data-stu-id="5f6e0-118">Valid</span></span>|<span data-ttu-id="5f6e0-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f6e0-119">ValidationStates</span></span>|<span data-ttu-id="5f6e0-120">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5f6e0-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5f6e0-121">InvalidFocused</span></span>|<span data-ttu-id="5f6e0-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f6e0-122">ValidationStates</span></span>|<span data-ttu-id="5f6e0-123">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5f6e0-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5f6e0-124">InvalidUnfocused</span></span>|<span data-ttu-id="5f6e0-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5f6e0-125">ValidationStates</span></span>|<span data-ttu-id="5f6e0-126">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="5f6e0-127">Frame-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f6e0-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="5f6e0-128">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Frame> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="5f6e0-129">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f6e0-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5f6e0-130">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5f6e0-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6e0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f6e0-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5f6e0-132">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="5f6e0-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5f6e0-133">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="5f6e0-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5f6e0-134">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5f6e0-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="5f6e0-135">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="5f6e0-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
