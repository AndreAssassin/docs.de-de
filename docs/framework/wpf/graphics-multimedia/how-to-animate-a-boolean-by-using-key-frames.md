---
title: 'Vorgehensweise: Animieren eines booleschen Werts mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 59a72916721cccbe66f704253f148828fa8cd418
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175031"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="bb73c-102">Vorgehensweise: Animieren eines booleschen Werts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="bb73c-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="bb73c-103">Dieses Beispiel zeigt, wie die boolesche Eigenschaft-Wert, der animiert ein <xref:System.Windows.Controls.Button> Steuerelement mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="bb73c-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb73c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb73c-104">Example</span></span>  
 <span data-ttu-id="bb73c-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.UIElement.IsEnabled%2A> Eigenschaft eine <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bb73c-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="bb73c-106">Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> Klasse.</span><span class="sxs-lookup"><span data-stu-id="bb73c-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="bb73c-107">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, die Verschiebung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="bb73c-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="bb73c-108">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="bb73c-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb73c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb73c-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="bb73c-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="bb73c-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="bb73c-111">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="bb73c-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
