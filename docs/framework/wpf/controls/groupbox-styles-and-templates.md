---
title: GroupBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 5ef8e4b44bc2b6072fa730f33c10191b64954f7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911260"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="37b56-102">GroupBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="37b56-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="37b56-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="37b56-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="37b56-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="37b56-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="37b56-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="37b56-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="37b56-106">GroupBox-Teile</span><span class="sxs-lookup"><span data-stu-id="37b56-106">GroupBox Parts</span></span>  
 <span data-ttu-id="37b56-107">Die <xref:System.Windows.Controls.GroupBox> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="37b56-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="37b56-108">GroupBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="37b56-108">GroupBox States</span></span>  
 <span data-ttu-id="37b56-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="37b56-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="37b56-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="37b56-110">VisualState Name</span></span>|<span data-ttu-id="37b56-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="37b56-111">VisualStateGroup Name</span></span>|<span data-ttu-id="37b56-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37b56-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="37b56-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="37b56-113">Valid</span></span>|<span data-ttu-id="37b56-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37b56-114">ValidationStates</span></span>|<span data-ttu-id="37b56-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="37b56-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="37b56-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="37b56-116">InvalidFocused</span></span>|<span data-ttu-id="37b56-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37b56-117">ValidationStates</span></span>|<span data-ttu-id="37b56-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="37b56-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="37b56-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="37b56-119">InvalidUnfocused</span></span>|<span data-ttu-id="37b56-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37b56-120">ValidationStates</span></span>|<span data-ttu-id="37b56-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="37b56-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="37b56-122">GroupBox-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="37b56-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="37b56-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="37b56-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="37b56-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="37b56-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="37b56-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="37b56-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b56-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37b56-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="37b56-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="37b56-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="37b56-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="37b56-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="37b56-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="37b56-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="37b56-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="37b56-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
