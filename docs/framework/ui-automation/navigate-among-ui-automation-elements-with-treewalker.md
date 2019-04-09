---
title: Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: aed8c624a75364dcc97c73ae7ebd6331275ceff4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182870"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="087a9-102">Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker</span><span class="sxs-lookup"><span data-stu-id="087a9-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
>  <span data-ttu-id="087a9-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="087a9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="087a9-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="087a9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="087a9-105">Dieses Thema enthält Beispielcode, der zeigt, wie Sie die Navigation zwischen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elemente mithilfe der <xref:System.Windows.Automation.TreeWalker> Klasse.</span><span class="sxs-lookup"><span data-stu-id="087a9-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="087a9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="087a9-106">Example</span></span>  
 <span data-ttu-id="087a9-107">Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetParent%2A> , durchlaufen Sie die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Struktur, bis das Stammelement oder den Desktop gefunden.</span><span class="sxs-lookup"><span data-stu-id="087a9-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="087a9-108">Das Element direkt unterhalb, ist das übergeordnete Fenster des angegebenen Elements.</span><span class="sxs-lookup"><span data-stu-id="087a9-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="087a9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="087a9-109">Example</span></span>  
 <span data-ttu-id="087a9-110">Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> und <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> zum Erstellen einer <xref:System.Windows.Forms.TreeView> mit eine kompletten Teilstruktur von aktuellem [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elemente, die sich in der Steuerelementansicht und die, die aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="087a9-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="087a9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="087a9-111">See also</span></span>

- [<span data-ttu-id="087a9-112">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="087a9-112">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
