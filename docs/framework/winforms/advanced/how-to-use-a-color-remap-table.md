---
title: 'Vorgehensweise: Verwenden einer Farbneuzuordnungstabelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 619eee8e5c08d24f2c7c485dfdc43331f5d64e9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080058"
---
# <a name="how-to-use-a-color-remap-table"></a>Vorgehensweise: Verwenden einer Farbneuzuordnungstabelle
Neuzuordnung ist der Prozess der Konvertierung der Farben eines Bilds gemäß einer Farbumwandlungstabelle. Die Farbumwandlungstabelle ist ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte. Jede <xref:System.Drawing.Imaging.ColorMap> Objekt im Array verfügt über eine <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft und eine <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft.  
  
 Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ein Bild zeichnet, jedes Pixel des Bilds in das Array der alten Farben verglichen wird. Wenn die Farbe eines Pixels eine alte Farbe übereinstimmt, wird seine Farbe in die entsprechende neue Farbe geändert. Die Farben werden nur für das Rendering geändert – die Farbwerte, der das Bild selbst (gespeichert einer <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt) werden nicht geändert.  
  
 Um ein neu zugeordnetes Bild zu zeichnen, initialisieren Sie ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte. Dieses Arrays zum Übergeben der <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> -Methode der ein <xref:System.Drawing.Imaging.ImageAttributes> Objekt, und klicken Sie dann übergeben die <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der ein <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei RemapInput.bmp. Der Code erstellt, eine Farbumwandlungstabelle an, die aus einer einzelnen besteht <xref:System.Drawing.Imaging.ColorMap> Objekt. Die <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft der `ColorRemap` Objekt ist rot, und die <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft ist Blau. Das Image ist gezeichneten einmal ohne und einmal mit neuzuordnung. Der neuzuordnung ändert die roten Pixel in Blau.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das neu zugeordnete Bild auf der rechten Seite an.  
  
 ![Screenshot, der anzeigt, das ursprüngliche Bild und das neu zugeordnete Bild.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch

- [Neufärben von Bildern](recoloring-images.md)
- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
