---
title: 'Gewusst wie: Erstellen einer Form mithilfe von PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452044"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>Gewusst wie: Erstellen einer Form mithilfe von PathGeometry
In diesem Beispiel wird gezeigt, wie eine Form mit der <xref:System.Windows.Media.PathGeometry>-Klasse erstellt wird. <xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten. jede <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar. Jede <xref:System.Windows.Media.PathFigure> besteht aus einem oder mehreren <xref:System.Windows.Media.PathSegment> Objekten, die jeweils einen verbundenen Teil der Abbildung oder Form darstellen. Zu den Segment Typen zählen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>und <xref:System.Windows.Media.BezierSegment>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.PathGeometry> zum Erstellen eines Dreiecks verwendet. Die <xref:System.Windows.Media.PathGeometry> wird mit einem <xref:System.Windows.Shapes.Path>-Element angezeigt.  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
Ein mit PathGeometry erstelltes Dreieck  
  
 Im vorherigen Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck, erstellt wird. Eine <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen zu erstellen, einschließlich Bögen und Kurven. Beispiele finden Sie unter [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md), [Erstellen einer kubischen Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md)und [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md).  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Übersicht über Geometrien](geometry-overview.md)
- [Beispiel für Geometry](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
