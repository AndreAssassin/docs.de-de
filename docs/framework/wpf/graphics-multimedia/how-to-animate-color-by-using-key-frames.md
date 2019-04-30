---
title: 'Vorgehensweise: Animieren von Color mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: e579c4beb757ccf58eb1b9ca1f3852a5b96cac1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010024"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="ed63c-102">Vorgehensweise: Animieren von Color mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="ed63c-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="ed63c-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="ed63c-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed63c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed63c-104">Example</span></span>  
 <span data-ttu-id="ed63c-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> Eigenschaft eine <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ed63c-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="ed63c-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="ed63c-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="ed63c-107">In den ersten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearColorKeyFrame> Klasse, um die Farbe allmählich von Grün zu Rot zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed63c-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="ed63c-108">Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearColorKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed63c-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="ed63c-109">Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> Klasse, um die Farbe schnell von Rot über Gelb zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ed63c-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="ed63c-110">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> abrupte Veränderungen zwischen Werten, d. h. erstellen, die farbveränderung in diesem Teil der Animation tritt schnell auf und ist.</span><span class="sxs-lookup"><span data-stu-id="ed63c-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="ed63c-111">In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineColorKeyFrame> Klasse, um die Farbe erneut zu ändern – in diesem Fall von Gelb zu Grün.</span><span class="sxs-lookup"><span data-stu-id="ed63c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="ed63c-112">Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineColorKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ed63c-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="ed63c-113">In diesem Beispiel beginnt die Farbveränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="ed63c-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ed63c-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="ed63c-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed63c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed63c-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="ed63c-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="ed63c-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="ed63c-117">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="ed63c-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
