---
title: 'Vorgehensweise: Treffertest in einem Viewport3D-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: c3238161a01df67b05be6284b8eed61981ff3974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098064"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="ad9a3-102">Vorgehensweise: Treffertest in einem Viewport3D-Objekt</span><span class="sxs-lookup"><span data-stu-id="ad9a3-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="ad9a3-103">Dieses Beispiel zeigt, wie ein Treffertest für 3D-Elemente in einem <xref:System.Windows.Controls.Viewport3D>.</span><span class="sxs-lookup"><span data-stu-id="ad9a3-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="ad9a3-104">Da <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D- und 3D-Spiele gibt Informationen zurück, es ist möglich, durchlaufen die Testergebnisse nur 3D Ergebnisse zu lesen.</span><span class="sxs-lookup"><span data-stu-id="ad9a3-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="ad9a3-105">Die <xref:System.Windows.Media.HitTestResultBehavior> in den folgenden Code bestimmt, wie die Treffertestergebnissen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ad9a3-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="ad9a3-106">`UpdateResultInfo` und `UpdateMaterial` lokal definierte Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="ad9a3-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a><span data-ttu-id="ad9a3-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad9a3-107">See also</span></span>

- [<span data-ttu-id="ad9a3-108">Drücken Sie Beispiel zu Leistungstests in 3D</span><span class="sxs-lookup"><span data-stu-id="ad9a3-108">3-D Hit Testing Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159959)
