---
title: 'Vorgehensweise: Zeichnen einer geschlossenen Form mithilfe des Polygon-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003235"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="0753d-102">Vorgehensweise: Zeichnen einer geschlossenen Form mithilfe des Polygon-Elements</span><span class="sxs-lookup"><span data-stu-id="0753d-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="0753d-103">Dieses Beispiel zeigt, wie Sie das Zeichnen einer geschlossenen Form mithilfe der <xref:System.Windows.Shapes.Polygon> Element.</span><span class="sxs-lookup"><span data-stu-id="0753d-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="0753d-104">Um eine geschlossene Form zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Polygon> -Element, und verwenden dessen <xref:System.Windows.Shapes.Polygon.Points%2A> -Eigenschaft an den Scheitelpunkten einer Form.</span><span class="sxs-lookup"><span data-stu-id="0753d-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="0753d-105">Automatisch wird eine Linie gezeichnet, die die ersten und letzten Punkte verbindet.</span><span class="sxs-lookup"><span data-stu-id="0753d-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="0753d-106">Geben Sie abschließend eine <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, oder beides.</span><span class="sxs-lookup"><span data-stu-id="0753d-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0753d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0753d-107">Example</span></span>  
 <span data-ttu-id="0753d-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von durch Trennzeichen getrennte x und y-Koordinate-Paaren.</span><span class="sxs-lookup"><span data-stu-id="0753d-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="0753d-109">Obwohl das Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Polygone enthalten, können Sie Polygon-Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0753d-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="0753d-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="0753d-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
