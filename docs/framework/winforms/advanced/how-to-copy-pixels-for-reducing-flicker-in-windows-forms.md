---
title: 'Vorgehensweise: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: e3d1c2b681e98dc7c45467683924dd4022eb377e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094033"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Vorgehensweise: Kopieren von Pixeln zum Vermindern des Flackerns in Windows Forms
Wenn Sie eine einfache Grafik animieren, können Benutzer manchmal Flimmern oder andere unerwünschte visuelle Effekte auftreten. Eine Möglichkeit zum Beschränken dieses Problems ist, einen "Bitblt" auf die Grafik verwenden. BitBlt ist die "Bitblocktransfer" der Farbdaten aus einem Ursprung Rechteck aus Pixeln einen Ziel-Rechteck aus Pixeln.  
  
 Mit Windows Forms, Bitblt erfolgt mithilfe der <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode der <xref:System.Drawing.Graphics> Klasse. In den Parametern der Methode geben Sie an der Quelle und Ziel (als Punkt), die Größe des Bereichs für den kopiert werden und das Graphics-Objekt verwendet, um die neue Form zu zeichnen.  
  
 Im folgenden Beispiel wird eine Form gezeichnet wird, auf dem Formular in der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Anschließend wird die <xref:System.Drawing.Graphics.CopyFromScreen%2A> Methode wird verwendet, um die Form zu duplizieren.  
  
> [!NOTE]
>  Festlegen des Formulars <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true` veranlasst grafikbasierte-Code in die <xref:System.Windows.Forms.Control.Paint> Ereignis werden doppelt gepufferte. Obwohl dies nicht über aller erkennbaren Leistungsgewinne besitzt, wenn Sie den folgenden Code verwenden, ist es etwas zu bedenken, bei der Arbeit mit komplexeren grafikbearbeitung Code.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Der obige Code ausgeführt wird, in der Form <xref:System.Windows.Forms.Control.Paint> -Ereignishandler so, dass die Grafiken erhalten bleiben, wenn das Formular neu gezeichnet wird. Rufen Sie daher nicht Grafiken bezogene Methoden in der <xref:System.Windows.Forms.Form.Load> -Ereignishandler, da der gezeichnete Inhalt nicht neu gezeichnet wird, wenn das Formular vergrößert bzw. verkleinert oder durch eine andere Form verdeckt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
