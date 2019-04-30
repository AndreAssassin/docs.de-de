---
title: 'Vorgehensweise: Steuern der Keyframe-Animationszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d0ea56b24f8fffeb688d297a675681bce3fdc4e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911514"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="cafdb-102">Vorgehensweise: Steuern der Keyframe-Animationszeit</span><span class="sxs-lookup"><span data-stu-id="cafdb-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="cafdb-103">Dieses Beispiel zeigt, wie Sie den zeitlichen Ablauf mit Keyframes innerhalb einer Keyframe Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="cafdb-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="cafdb-104">Wie andere Animationen, verfügen auch Keyframe-Animationen eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cafdb-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="cafdb-105">Zusätzlich zur Angabe der Dauer einer Animation, müssen Sie angeben, welcher Teil dieser Dauer aller zugehörigen Keyframes zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cafdb-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="cafdb-106">Um die Zeit zuzuweisen, geben Sie einen <xref:System.Windows.Media.Animation.KeyTime> für jeden Keyframe der Animation.</span><span class="sxs-lookup"><span data-stu-id="cafdb-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="cafdb-107">Die <xref:System.Windows.Media.Animation.KeyTime> für jedes Keyframes gibt an, wenn ein Keyframe endet (es gibt keinen die Zeitspanne, die Wiedergabedauer eines Keyframes).</span><span class="sxs-lookup"><span data-stu-id="cafdb-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="cafdb-108">Können Sie angeben, ein <xref:System.Windows.Media.Animation.KeyTime> als eine <xref:System.TimeSpan> Wert, der als Prozentsatz oder als die <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> besonderen Wert.</span><span class="sxs-lookup"><span data-stu-id="cafdb-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="cafdb-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cafdb-109">Example</span></span>

<span data-ttu-id="cafdb-110">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> um ein Rechteck auf dem Bildschirm zu animieren.</span><span class="sxs-lookup"><span data-stu-id="cafdb-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="cafdb-111">Schlüsselzeiten für Keyframes festgelegt werden, mit <xref:System.TimeSpan> Werte.</span><span class="sxs-lookup"><span data-stu-id="cafdb-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="cafdb-112">Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cafdb-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="cafdb-113">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="cafdb-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="cafdb-114">Das nächste Beispiel zeigt eine Animation, die identisch ist, jedoch mit Prozentwerten Schlüsselzeiten für Keyframes festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cafdb-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="cafdb-115">Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cafdb-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="cafdb-116">![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="cafdb-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="cafdb-117">Im nächsten Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key Time-Werten.</span><span class="sxs-lookup"><span data-stu-id="cafdb-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="cafdb-118">Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cafdb-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="cafdb-119">![Schlüsselwerte werden am 3.3,6.6, 6,6 und 9,9 Sekunden erreicht](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="cafdb-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="cafdb-120">Im letzten Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key Time-Werten.</span><span class="sxs-lookup"><span data-stu-id="cafdb-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="cafdb-121">Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cafdb-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="cafdb-122">![Schlüsselwerte werden auf 0, 5 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="cafdb-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="cafdb-123">Der Einfachheit halber die Codeversionen dieses Beispiels lokale Animationen, storyboards, da nur eine einzelne Animation auf eine einzelne Eigenschaft angewendet wird, aber in den Beispielen können geändert werden, um Storyboards zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cafdb-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="cafdb-124">Ein Beispiel, wie Sie ein Storyboard im Code deklarieren, finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="cafdb-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="cafdb-125">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="cafdb-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="cafdb-126">Weitere Informationen zu den Keyframe-Animationen, finden Sie unter den [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cafdb-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cafdb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cafdb-127">See also</span></span>

- [<span data-ttu-id="cafdb-128">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="cafdb-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="cafdb-129">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="cafdb-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="cafdb-130">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="cafdb-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
