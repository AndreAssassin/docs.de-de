---
title: Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 9183aecdc47d54aef26d5cdca8ea11d8398be732
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226507"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="3c6d0-102">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="3c6d0-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="3c6d0-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3c6d0-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3c6d0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3c6d0-105">Dieses Thema enthält Beispielcode, der zeigt, wie Sie mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Einfügen von Text in einem einzeiligen Textfeld.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="3c6d0-106">Eine alternative Methode für mehrzeilige und rich-Text-Steuerelemente bereitgestellt wird, in denen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist nicht anwendbar.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="3c6d0-107">Für Vergleichszwecke können veranschaulicht das Beispiel auch Win32-Methoden verwenden, um dieselben Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c6d0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c6d0-108">Example</span></span>  
 <span data-ttu-id="3c6d0-109">Im folgenden Beispiel Durchlaufen einer Sequenz von Textsteuerelementen in einer Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="3c6d0-110">Jedes Textfeld-Steuerelement wird daraufhin überprüft, ob eine <xref:System.Windows.Automation.ValuePattern> -Objekt abgerufen werden kann, mithilfe der <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="3c6d0-111">Wenn das Steuerelement unterstützt <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> Methode wird verwendet, um eine benutzerdefinierte Zeichenfolge in das Textsteuerelement einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="3c6d0-112">Andernfalls die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> Methode wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c6d0-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="3c6d0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c6d0-113">See also</span></span>

- <span data-ttu-id="3c6d0-114">[Beispiel für TextPattern Insert Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3c6d0-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
