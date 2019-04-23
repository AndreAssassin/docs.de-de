---
title: 'Vorgehensweise: Erstellen einer kubischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115569"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Vorgehensweise: Erstellen einer kubischen Bézierkurve
Dieses Beispiel zeigt, wie Sie eine kubische Bezier-Kurve zu erstellen. Verwenden Sie zum Erstellen einer kubischen Bezier-Kurve der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.BezierSegment> Klassen.  Verwenden Sie zum Anzeigen der resultierenden Geometrie eine <xref:System.Windows.Shapes.Path> -Element, oder verwenden Sie es mit einer <xref:System.Windows.Media.GeometryDrawing> oder ein <xref:System.Windows.Media.DrawingContext>. In den folgenden Beispielen wird von eine kubische Bezier-Kurve gezeichnet (10, 100), (300, 100). Die Kurve hat der Control-Punkte ("100", "0") und (200, 200).  
  
## <a name="example"></a>Beispiel  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], können Sie abgekürzte Markupsyntax zum Beschreiben eines Pfads.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine kubische Bezier-Kurve Objekttags zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md)
- [Erstellen eines LineSegment in einer PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Erstellen Sie eine kubische Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md)
- [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md)
