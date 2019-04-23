---
title: 'Vorgehensweise: Zeichnen von kardinalen Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 2f03177bf97936a2ca9558972d4d82fa3e07463c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204951"
---
# <a name="how-to-draw-cardinal-splines"></a>Vorgehensweise: Zeichnen von kardinalen Splines
Eine cardinal-Splinekurve ist eine Kurve, die einen bestimmten Satz von Punkten reibungslos zu durchlaufen. Um eine cardinal-Splinekurve zu zeichnen, erstellen eine <xref:System.Drawing.Graphics> Objekt, und übergeben Sie die Adresse eines Arrays von Punkten um die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Zeichnen eines glockenförmigen kardinalen Splines  
  
-   Im folgende Beispiel zeichnet eine glockenförmigen cardinal-Splinekurve, die fünf angegebenen Punkte durchlaufen. Die folgende Abbildung zeigt die Kurve und fünf Punkte.  
  
     ![Das Diagramm, das eine glockenförmigen cardinal-Splinekurve anzeigt.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Zeichnen einer geschlossenen kardinalen Splines  
  
-   Verwenden der <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode der <xref:System.Drawing.Graphics> Klasse, um eine geschlossene cardinal-Splinekurve zu zeichnen. In einer geschlossenen cardinal-Splinekurve die Kurve wird fortgesetzt, bis der letzte Punkt im Array und eine Verbindung mit den ersten Punkt im Array. Im folgende Beispiel zeichnet eine geschlossene cardinal-Splinekurve, die sechs angegebenen Punkte durchlaufen. Die folgende Abbildung zeigt die geschlossene Splinekurve, die zusammen mit den sechs Punkten:  
  
 ![Das Diagramm, die eine geschlossene cardinal-Splinekurve anzeigt.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Ändern der Krümmung eines kardinalen Splines  
  
-   Ändern Sie die Möglichkeit, eine cardinal-Splinekurve durch Übergeben eines Arguments Spannung zu sanftesten, der <xref:System.Drawing.Graphics.DrawCurve%2A> Methode. Im folgende Beispiel zeichnet drei kardinale Splinekurven, die über den gleichen Satz von Punkten übergeben. Die folgende Abbildung zeigt die drei Splines zusammen mit ihren Spannungswerten. Beachten Sie, wenn die Spannung 0 ist, die Punkte durch gerade Linien verbunden sind.  
  
 ![Das Diagramm, das drei kardinale Splinekurven anzeigt.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Im vorherigen Beispiel sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Erstellen und Zeichnen von Kurven](constructing-and-drawing-curves.md)
