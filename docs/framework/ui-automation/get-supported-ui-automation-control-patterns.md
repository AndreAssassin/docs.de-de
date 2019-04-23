---
title: Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 64c5bae738cee5249e6c2406a2f94667ecb2931f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337018"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="f1f8f-102">Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="f1f8f-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="f1f8f-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f1f8f-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f1f8f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f1f8f-105">In diesem Thema wird gezeigt, wie Steuerelementmusterobjekte aus [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Elementen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="f1f8f-106">Abrufen aller Steuerelementmuster</span><span class="sxs-lookup"><span data-stu-id="f1f8f-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="f1f8f-107">Rufen Sie das <xref:System.Windows.Automation.AutomationElement>-Objekt ab, an dessen Steuerelementmustern Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="f1f8f-108">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> auf, um alle Steuerelementmuster aus dem Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f1f8f-109">Ein Client sollte auf keinen Fall <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="f1f8f-110">Die Leistung kann schwerwiegend beeinträchtigt werden, da diese Methode intern <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für jedes vorhandene Steuerelementmuster aufruft.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="f1f8f-111">Wenn möglich sollte ein Client <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für die gewünschten Steuerelementmuster aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="f1f8f-112">Abrufen eines bestimmten Steuerelementmusters</span><span class="sxs-lookup"><span data-stu-id="f1f8f-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="f1f8f-113">Rufen Sie das <xref:System.Windows.Automation.AutomationElement>-Objekt ab, an dessen Steuerelementmustern Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="f1f8f-114">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> auf, um auf ein bestimmtes Muster abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="f1f8f-115">Diese Methoden ähneln sich, wenn das Muster aber nicht gefunden wird, löst <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> eine Ausnahme aus, während <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> den Wert `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1f8f-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1f8f-116">Example</span></span>  
 <span data-ttu-id="f1f8f-117">Im folgenden Beispiel wird ein <xref:System.Windows.Automation.AutomationElement> für ein Listenelement und aus diesem Element ein <xref:System.Windows.Automation.SelectionItemPattern> abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f1f8f-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="f1f8f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1f8f-118">See also</span></span>

- [<span data-ttu-id="f1f8f-119">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="f1f8f-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
