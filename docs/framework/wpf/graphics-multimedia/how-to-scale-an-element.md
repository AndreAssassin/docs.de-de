---
title: 'Vorgehensweise: Skalieren eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 607b3a11085f746503c1b82552f1740b49d9ef5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131702"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="6b5a4-102">Vorgehensweise: Skalieren eines Elements</span><span class="sxs-lookup"><span data-stu-id="6b5a4-102">How to: Scale an Element</span></span>
<span data-ttu-id="6b5a4-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ScaleTransform> ein Element skalieren.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="6b5a4-104">Verwenden der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften zum Ändern der Größe des Elements durch der Faktor für die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="6b5a4-105">Z. B. eine <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Wert von 1,5 wird das Element auf 150 Prozent der ursprünglichen Breite gestreckt.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="6b5a4-106">Ein <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Wert von 0,5 verringert sich die Höhe eines Elements um 50 Prozent.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="6b5a4-107">Verwenden der <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> Eigenschaften, die den Punkt angeben, die den Mittelpunkt des skalierungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="6b5a4-108">Standardmäßig eine <xref:System.Windows.Media.ScaleTransform> basiert, an dem Punkt (0,0), das die linke obere Ecke des Rechtecks entspricht.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="6b5a4-109">Dies wirkt sich das Element verschoben wird und er größer angezeigt werden, weil beim Anwenden einer <xref:System.Windows.Media.Transform>, Sie ändern den Koordinatenbereich, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="6b5a4-110">Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> verdoppeln Sie die Größe des eine 50 x 50 <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="6b5a4-111">Die <xref:System.Windows.Media.ScaleTransform> hat den Wert 0 (Standard) für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b5a4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b5a4-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="6b5a4-113">Legen Sie in der Regel <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> in der Mitte des Objekts, das skaliert wird: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="6b5a4-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="6b5a4-114">Das folgende Beispiel zeigt eine andere <xref:System.Windows.Shapes.Rectangle> , Größe verdoppelt wird jedoch dadurch <xref:System.Windows.Media.ScaleTransform> hat den Wert 25 für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, in der Mitte des Rechtecks entspricht.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="6b5a4-115">Die folgende Abbildung zeigt den Unterschied zwischen den beiden <xref:System.Windows.Media.ScaleTransform> Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="6b5a4-116">Die gepunktete Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.</span><span class="sxs-lookup"><span data-stu-id="6b5a4-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="6b5a4-117">![2-fach-Skalierung mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-scalecenter.gif "Wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="6b5a4-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="6b5a4-118">Zwei ScaleTransform-Vorgänge mit identischen ScaleX- und ScaleY-Werten aber unterschiedlichen Mittelpunkten</span><span class="sxs-lookup"><span data-stu-id="6b5a4-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="6b5a4-119">Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="6b5a4-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5a4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b5a4-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="6b5a4-121">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="6b5a4-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="6b5a4-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6b5a4-122">How-to Topics</span></span>](transformations-how-to-topics.md)
