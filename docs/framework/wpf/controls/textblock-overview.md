---
title: Übersicht über TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203469"
---
# <a name="textblock-overview"></a><span data-ttu-id="ecd56-102">Übersicht über TextBlock</span><span class="sxs-lookup"><span data-stu-id="ecd56-102">TextBlock Overview</span></span>
<span data-ttu-id="ecd56-103">Die <xref:System.Windows.Controls.TextBlock> Steuerelement bietet flexible textunterstützung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ecd56-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="ecd56-104">Es eignet sich hauptsächlich für einfache [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios, in denen nicht mehr Text als ein Absatz benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ecd56-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="ecd56-105">Unterstützt eine Reihe von Eigenschaften, mit denen präzise gesteuert, wie z. B. <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, und <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span><span class="sxs-lookup"><span data-stu-id="ecd56-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="ecd56-106">Text-Inhalt kann hinzugefügt werden, mithilfe der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ecd56-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="ecd56-107">Bei der Verwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird der Inhalt zwischen dem öffnenden und dem schließenden Tag implizit als Text des Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecd56-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="ecd56-108">Ein <xref:System.Windows.Controls.TextBlock> Element kann instanziiert werden, sehr einfach mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd56-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="ecd56-109">Auf ähnliche Weise die Verwendung von der <xref:System.Windows.Controls.TextBlock> Element im Code ist relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="ecd56-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ecd56-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecd56-110">See also</span></span>

- <xref:System.Windows.Controls.Label>
