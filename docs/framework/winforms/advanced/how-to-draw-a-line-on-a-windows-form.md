---
title: 'Vorgehensweise: Zeichnen einer Linie in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: aab04b9236175cedd154b817db5a6f6450503105
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074448"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Vorgehensweise: Zeichnen einer Linie in Windows Forms
In diesem Beispiel zeichnet eine Linie in einem Formular. In der Regel, wenn Sie in einem Formular zeichnen, behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis und führen Sie das Zeichnen mit der <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft der <xref:System.Windows.Forms.PaintEventArgs>, wie im folgenden Beispiel gezeigt  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Pen> Objekte.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Erste Schritte mit Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
