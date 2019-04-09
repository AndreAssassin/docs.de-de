---
title: 'Vorgehensweise: Überschreiben der Panel.OnRender-Methode'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102530"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="b718d-102">Vorgehensweise: Überschreiben der Panel.OnRender-Methode</span><span class="sxs-lookup"><span data-stu-id="b718d-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="b718d-103">Dieses Beispiel veranschaulicht das Überschreiben der <xref:System.Windows.Controls.Panel.OnRender%2A> -Methode der <xref:System.Windows.Controls.Panel> damit benutzerdefinierte grafische Effekte ein Layoutelement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b718d-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b718d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b718d-104">Example</span></span>  
 <span data-ttu-id="b718d-105">Verwenden der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode, um einen gerenderten Bereichselements grafische Effekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b718d-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="b718d-106">Diese Methode können Sie z. B. benutzerdefinierten Rahmen oder Hintergrundeffekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b718d-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="b718d-107">Ein <xref:System.Windows.Media.DrawingContext> Objekt als Argument, das Methoden zum Zeichnen von Formen, Text, Bilder oder Videos enthält übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b718d-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="b718d-108">Diese Methode eignet sich daher für die Anpassung von ein-Objekt.</span><span class="sxs-lookup"><span data-stu-id="b718d-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b718d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b718d-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="b718d-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b718d-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b718d-111">Benutzerdefinierte Radial Panel Sample</span><span class="sxs-lookup"><span data-stu-id="b718d-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="b718d-112">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="b718d-112">How-to Topics</span></span>](panel-how-to-topics.md)
