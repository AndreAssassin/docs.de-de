---
title: 'Vorgehensweise: Zeichnen einer Linie'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: c11dfb9523834ec2e622cb2e62bd6982a1a78fd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143519"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="fab06-102">Vorgehensweise: Zeichnen einer Linie</span><span class="sxs-lookup"><span data-stu-id="fab06-102">How to: Draw a Line</span></span>
<span data-ttu-id="fab06-103">Dieses Beispiel zeigt, wie zum Zeichnen von Linien mit dem <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="fab06-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="fab06-104">Um eine Linie zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="fab06-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="fab06-105">Verwenden Sie die <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A> Eigenschaften legen Sie dessen Start, zeigen Sie; und verwenden dessen <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A> Eigenschaften legen Sie seinen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="fab06-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="fab06-106">Legen Sie schließlich die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> da eine Zeile ohne einen Strich nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="fab06-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="fab06-107">Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> -Element für eine Zeile hat keine Auswirkungen, da es sich bei eine Zeile keine Inneres hat.</span><span class="sxs-lookup"><span data-stu-id="fab06-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="fab06-108">Das folgende Beispiel zeichnet drei Linien in einem <xref:System.Windows.Controls.Canvas> Element.</span><span class="sxs-lookup"><span data-stu-id="fab06-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fab06-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fab06-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="fab06-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="fab06-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab06-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fab06-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="fab06-112">Formelemente</span><span class="sxs-lookup"><span data-stu-id="fab06-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
