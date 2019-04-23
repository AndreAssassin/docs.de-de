---
title: Polygone in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132625"
---
# <a name="polygons-in-gdi"></a>Polygone in GDI+
Ein Polygon ist eine geschlossene Form mit drei oder mehr gerade Seiten. Z. B. ein Dreieck ist ein Polygon mit drei Seiten, ein Rechteck ist ein Polygon mit vier Seiten und ein Fünfeck ist ein Polygon mit fünf Seiten. Die folgende Abbildung zeigt verschiedene Polygone.  
  
 ![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Zeichnen eines Polygons  
 Um ein Polygon zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt eine <xref:System.Drawing.Pen> Objekt und ein Array von <xref:System.Drawing.Point> (oder <xref:System.Drawing.PointF>) Objekte. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode. Die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um das Polygon, und das Array von Rendern <xref:System.Drawing.Point> -Objekte speichert, die Punkte durch gerade Linien miteinander verbunden werden. Die <xref:System.Drawing.Pen> Objekt und das Array von <xref:System.Drawing.Point> Objekte werden als Argumente übergeben die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode. Im folgende Beispiel zeichnet ein Vieleck, drei Seiten. Beachten Sie, dass es nur drei Punkte im `myPointArray`: (0, 0), (50, 30), und (30, 60). Die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode schließt automatisch das Polygon durch Zeichnen einer Linie aus (30, 60) wieder zum Ausgangspunkt (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Die folgende Abbildung zeigt das Polygon.  
  
 ![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Erstellen eines Stifts](how-to-create-a-pen.md)
