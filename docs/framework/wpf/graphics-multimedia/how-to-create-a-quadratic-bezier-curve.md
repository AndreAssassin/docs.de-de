---
title: 'Vorgehensweise: Erstellen einer quadratischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: a0b2145b4a5bba11186419fe680f2eca41949d6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134872"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="61873-102">Vorgehensweise: Erstellen einer quadratischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="61873-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="61873-103">Dieses Beispiel zeigt, wie Sie eine quadratische Bezierkurve zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61873-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="61873-104">Verwenden Sie zum Erstellen einer quadratischen Bezierkurve der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.QuadraticBezierSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="61873-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61873-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61873-105">Example</span></span>  
 <span data-ttu-id="61873-106">In den folgenden Beispielen wird eine quadratische Bezierkurve (300,100) von (10,100) positioniert.</span><span class="sxs-lookup"><span data-stu-id="61873-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="61873-107">Die Kurve hat ein Steuerungspunkts für bei (200,200) enthält.</span><span class="sxs-lookup"><span data-stu-id="61873-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="61873-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="61873-108">[xaml]</span></span>  
  
 <span data-ttu-id="61873-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können zum Beschreiben eines Pfads Attributsyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="61873-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="61873-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="61873-110">[xaml]</span></span>  
  
 <span data-ttu-id="61873-111">(Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="61873-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="61873-112">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="61873-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="61873-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine quadratische Bezier-Kurve, die mithilfe von Objektelementsyntax zeichnen.</span><span class="sxs-lookup"><span data-stu-id="61873-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="61873-114">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="61873-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="61873-115">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="61873-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61873-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61873-116">See also</span></span>

- [<span data-ttu-id="61873-117">Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="61873-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="61873-118">Erstellen einer kubischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="61873-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
