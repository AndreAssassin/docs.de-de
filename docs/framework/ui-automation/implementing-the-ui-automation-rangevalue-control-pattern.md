---
title: Implementieren des RangeValue-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: bb486dc210bc2d03be6400e9fe5c80b2a7c1de8e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659871"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="29735-102">Implementieren des RangeValue-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="29735-102">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="29735-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="29735-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="29735-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="29735-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="29735-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IRangeValueProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="29735-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="29735-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="29735-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="29735-107">Das <xref:System.Windows.Automation.RangeValuePattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die auf einen Wert innerhalb eines Bereichs festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="29735-107">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="29735-108">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="29735-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="29735-109">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="29735-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="29735-110">Beachten Sie beim Implementieren des RangeValue-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="29735-110">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="29735-111">Steuerelemente lassen eine erneute Kalibrierung der unterstützten Eigenschaften auf Grundlage des Gebietsschemas oder einer Benutzereinstellung zu.</span><span class="sxs-lookup"><span data-stu-id="29735-111">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="29735-112">Ein Beispiel hierfür ist ein Thermometersteuerelement, das so festgelegt werden kann, dass die Temperatur in Fahrenheit oder Celsius angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="29735-112">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="29735-113">Für Steuerelemente, die über mehrdeutige Bereichswerte verfügen, z. B. Statusanzeigen oder Schieberegler, sollten diese Werte normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="29735-113">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="29735-114">![Statusanzeige. ](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="29735-114">![Progress bar.](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="29735-115">Beispiel für eine Statusanzeige, in der der Wert eine ganze Zahl ist und die minimalen und maximalen Eigenschaftswerte auf 0 (null) beziehungsweise 100 normalisiert werden</span><span class="sxs-lookup"><span data-stu-id="29735-115">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>   
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="29735-116">Erforderliche Member für „IRangeValueProvider“</span><span class="sxs-lookup"><span data-stu-id="29735-116">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="29735-117">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="29735-117">Required member</span></span>|<span data-ttu-id="29735-118">Memberart</span><span class="sxs-lookup"><span data-stu-id="29735-118">Member type</span></span>|<span data-ttu-id="29735-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29735-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="29735-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-120">Property</span></span>|<span data-ttu-id="29735-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-121">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="29735-122">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-122">Property</span></span>|<span data-ttu-id="29735-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="29735-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-124">Property</span></span>|<span data-ttu-id="29735-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="29735-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-126">Property</span></span>|<span data-ttu-id="29735-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="29735-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-128">Property</span></span>|<span data-ttu-id="29735-129">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="29735-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="29735-130">Property</span></span>|<span data-ttu-id="29735-131">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="29735-132">Methoden</span><span class="sxs-lookup"><span data-stu-id="29735-132">Methods</span></span>|<span data-ttu-id="29735-133">Keiner</span><span class="sxs-lookup"><span data-stu-id="29735-133">None</span></span>|  
  
 <span data-ttu-id="29735-134">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="29735-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="29735-135">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="29735-135">Exceptions</span></span>  
 <span data-ttu-id="29735-136">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="29735-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="29735-137">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="29735-137">Exception type</span></span>|<span data-ttu-id="29735-138">Bedingung</span><span class="sxs-lookup"><span data-stu-id="29735-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="29735-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> wird mit einem Wert aufgerufen, der entweder größer als <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> oder kleiner als <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>ist.</span><span class="sxs-lookup"><span data-stu-id="29735-139"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29735-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29735-140">See also</span></span>

- [<span data-ttu-id="29735-141">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="29735-141">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="29735-142">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="29735-142">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="29735-143">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="29735-143">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="29735-144">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="29735-144">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="29735-145">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="29735-145">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
