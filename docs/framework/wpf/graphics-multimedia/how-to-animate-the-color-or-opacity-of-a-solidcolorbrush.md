---
title: 'Vorgehensweise: Animieren der Farbe oder der Durchlässigkeit von einem SolidColorBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: e440cf49b8b16051361650f9659dc6006c2e7b56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072158"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="3124e-102">Vorgehensweise: Animieren der Farbe oder der Durchlässigkeit von einem SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="3124e-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="3124e-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="3124e-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3124e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3124e-104">Example</span></span>  
 <span data-ttu-id="3124e-105">Im folgende Beispiel werden drei Animationen verwendet, zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="3124e-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="3124e-106">Der ersten Animation, einer <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels auf <xref:System.Windows.Media.Colors.Gray%2A> Wenn die Maus in das Rechteck eintritt.</span><span class="sxs-lookup"><span data-stu-id="3124e-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="3124e-107">Der nächsten Animation, einer anderen <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels auf <xref:System.Windows.Media.Colors.Orange%2A> Wenn sich der Mauszeiger in des Rechtecks.</span><span class="sxs-lookup"><span data-stu-id="3124e-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="3124e-108">Der letzten Animation, einer <xref:System.Windows.Media.Animation.DoubleAnimation>, wird die Durchlässigkeit des Pinsels zu 0,0 geändert, wenn die linke Maustaste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="3124e-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="3124e-109">Ein ausführlicheres Beispiel, zeigt, wie sich unterschiedliche Pinseltypen animiert, finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="3124e-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="3124e-110">Weitere Informationen zur Animation finden Sie unter den [Übersicht über Animationen](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3124e-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="3124e-111">Verwenden Sie für Konsistenz mit anderen Animationsbeispielen die Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt zum Anwenden der Animationen.</span><span class="sxs-lookup"><span data-stu-id="3124e-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="3124e-112">Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="3124e-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="3124e-113">Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="3124e-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3124e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3124e-114">See also</span></span>

- [<span data-ttu-id="3124e-115">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="3124e-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3124e-116">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="3124e-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="3124e-117">Beispiel für Pinsel</span><span class="sxs-lookup"><span data-stu-id="3124e-117">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
