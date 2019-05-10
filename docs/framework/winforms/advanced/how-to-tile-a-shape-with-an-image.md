---
title: 'Vorgehensweise: Anordnen einer Form neben bzw. unter einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063739"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Vorgehensweise: Anordnen einer Form neben bzw. unter einem Bild
Genau wie Kacheln ein Fußboden nebeneinander platziert werden können, können rechteckige Images Fill (Kachel) eine Form nebeneinander platziert werden. Verwenden Sie, um das Innere einer Form Kachel, eines Pinsels Textur. Beim Erstellen einer <xref:System.Drawing.TextureBrush> Objekt ist, wird eines der Argumente, die Sie an den Konstruktor übergeben, wird ein <xref:System.Drawing.Image> Objekt. Wenn Sie den Texturpinsel verwenden, um das Innere einer Form zu zeichnen, wird die Form durch wiederholte Kopien dieses Bilds gefüllt.  
  
 Der Wrap-Mode-Eigenschaft von der <xref:System.Drawing.TextureBrush> Objekt bestimmt, wie das Bild ausgerichtet ist, wie es in einem rechteckigen Raster wiederholt wird. Können Sie alles, was die Kacheln im Raster die gleiche Ausrichtung vornehmen können, oder Sie das Image von einer Rasterseite Position zum nächsten zu kippen. Die kippen möglich horizontal, vertikal oder beides. Die folgenden Beispiele veranschaulichen die Kacheln mit unterschiedlichen Arten von kippen.  
  
### <a name="to-tile-an-image"></a>Ein Bild gekachelt  
  
- Dieses Beispiel verwendet die folgende Abbildung 75 × 75 zu einem Rechteck 200 x 200-Kachel.  
  
 ![Die Kachel-Bild, das ein Rot Haus und einer Struktur anzeigt.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- Die folgende Abbildung zeigt, wie das Rechteck mit dem Image gekachelt wird. Beachten Sie, dass alle Kacheln die gleiche Ausrichtung; Es gibt kein Kippen verwendet.  
  
 ![Ein Rechteck mit dem Image mithilfe der gleichen Ausrichtung für alle Kacheln angeordnet.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Um ein Bild in Kacheln horizontal kippen  
  
- Dieses Beispiel verwendet das gleiche Bild für die 75 × 75 ein 200 x 200 Rechteck ausgefüllt. Der Umbruchmodus wird festgelegt, um das Bild horizontal gekippt. Die folgende Abbildung zeigt, wie das Rechteck mit dem Image gekachelt wird. Beachten Sie, wie Sie von einer Kachel in den nächsten in einer angegebenen Zeile verschieben, wird das Bild horizontal gekippt.  
  
 ![Ein Rechteck von tiled mit das Bild horizontal gekippt.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Um ein Bild in Kacheln vertikal kippen  
  
- Dieses Beispiel verwendet das gleiche Bild für die 75 × 75 ein 200 x 200 Rechteck ausgefüllt. Der Umbruchmodus wird festgelegt, um das Bild vertikal gekippt.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Um ein Bild Kacheln horizontal und vertikal kippen  
  
- Dieses Beispiel verwendet die gleichen 75 × 75-Image zu einem Rechteck 200 x 200-Kachel. Der Umbruchmodus wird festgelegt, das Bild horizontal und vertikal gekippt. Die folgende Abbildung zeigt, wie das Rechteck das Image gekachelt wird. Beachten Sie, wie Sie von einer Kachel in den nächsten in einer angegebenen Zeile verschieben, die das Bild horizontal gekippt wird, und wie Sie von einer Kachel in den nächsten in einer bestimmten Spalte verschieben, wird das Bild vertikal gekippt.  
  
 ![Ein Rechteck mit dem Bild gedreht wird, horizontal und vertikal angeordnet.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels zum Ausfüllen von Formen](using-a-brush-to-fill-shapes.md)
