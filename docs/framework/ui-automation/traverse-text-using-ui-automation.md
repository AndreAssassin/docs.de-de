---
title: Durchlaufen von Text mit Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: d73ae4ca11d6f5417bb5cb768eae4e586538bd92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154790"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="6adab-102">Durchlaufen von Text mit Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="6adab-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="6adab-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6adab-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6adab-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6adab-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6adab-105">In diesem Thema wird die Verwendung der [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Durchlaufen des Textinhalts eines Dokuments durch <xref:System.Windows.Automation.Text.TextUnit> -Inkremente veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6adab-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6adab-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6adab-106">Example</span></span>  
 <span data-ttu-id="6adab-107">Im folgenden Codebeispiel wird gezeigt, wie der Inhalt eines Benutzeroberflächenautomatisierungs-Textanbieters durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="6adab-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="6adab-108">Die <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> -Methode verschiebt die <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> - und <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> -Endpunkte eines <xref:System.Windows.Automation.Text.TextPatternRange>.</span><span class="sxs-lookup"><span data-stu-id="6adab-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="6adab-109">Dieser Textbereich ist üblicherweise ein degenerierter Bereich, der die Einfügemarke darstellt.</span><span class="sxs-lookup"><span data-stu-id="6adab-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6adab-110">Da nur textbasierte eingebettete Objekte als Teil des Textstreams betrachtet werden, haben eingebettete Objekte keine Auswirkung auf `Move` oder dessen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="6adab-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="6adab-111">Jede Methode, die <xref:System.Windows.Automation.Text.TextUnit> verwendet, wird bis zur nächstgrößeren unterstützten <xref:System.Windows.Automation.Text.TextUnit> zurückgestellt, wenn die angegebene <xref:System.Windows.Automation.Text.TextUnit> vom Steuerelement nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6adab-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adab-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6adab-112">See also</span></span>

- [<span data-ttu-id="6adab-113">Übersicht über TextPattern für die Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="6adab-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)
- [<span data-ttu-id="6adab-114">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="6adab-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="6adab-115">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="6adab-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="6adab-116">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="6adab-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="6adab-117">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="6adab-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
