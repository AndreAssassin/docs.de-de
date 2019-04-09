---
title: 'Vorgehensweise: Erstellen einer zusammengesetzten Zeichnung'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132469"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="0cc74-102">Vorgehensweise: Erstellen einer zusammengesetzten Zeichnung</span><span class="sxs-lookup"><span data-stu-id="0cc74-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="0cc74-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.DrawingGroup> komplexe Zeichnungen erstellen, durch die Kombination mehrerer <xref:System.Windows.Media.Drawing> Objekte in einer zusammengesetzten Zeichnung.</span><span class="sxs-lookup"><span data-stu-id="0cc74-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cc74-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cc74-104">Example</span></span>  
 <span data-ttu-id="0cc74-105">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> erstellen Sie eine zusammengesetzte Zeichnung aus der <xref:System.Windows.Media.GeometryDrawing> und <xref:System.Windows.Media.ImageDrawing> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0cc74-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="0cc74-106">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0cc74-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0cc74-107">![Eine DrawingGroup mit mehreren Zeichnungen](./media/graphicsmm-simple.jpg "Graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="0cc74-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="0cc74-108">Eine zusammengesetzte Zeichnung, die erstellt wird, mithilfe von DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="0cc74-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="0cc74-109">Beachten Sie den grauen Rahmen, der die Begrenzungen der Zeichnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0cc74-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="0cc74-110">Können Sie eine <xref:System.Windows.Media.DrawingGroup> Anwenden einer <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> festlegen, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, oder <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> auf die Zeichnungen, er enthält.</span><span class="sxs-lookup"><span data-stu-id="0cc74-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="0cc74-111">Da eine <xref:System.Windows.Media.DrawingGroup> ist auch eine <xref:System.Windows.Media.Drawing>, andere <xref:System.Windows.Media.DrawingGroup> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0cc74-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="0cc74-112">Im folgende Beispiel ähnelt dem vorherigen Beispiel, jedoch zusätzliche verwendet <xref:System.Windows.Media.DrawingGroup> Objekte Bitmapeffekten und eine Deckkraftmaske auf einige der Zeichnungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="0cc74-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="0cc74-113">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0cc74-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0cc74-114">![Eine DrawingGroup mit mehreren Zeichnungen](./media/graphicsmm-multiple.jpg "Graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="0cc74-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="0cc74-115">Zusammengesetzte Zeichnung, die über mehrere DrawingGroup-Objekte verfügt.</span><span class="sxs-lookup"><span data-stu-id="0cc74-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="0cc74-116">Beachten Sie den grauen Rahmen, der die Begrenzungen der Zeichnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0cc74-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="0cc74-117">Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0cc74-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc74-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cc74-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="0cc74-119">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="0cc74-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
