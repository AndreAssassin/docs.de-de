---
title: 'Vorgehensweise: Zeichnen einer mit einer Textur ausgefüllten Linie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004292"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="b117a-102">Vorgehensweise: Zeichnen einer mit einer Textur ausgefüllten Linie</span><span class="sxs-lookup"><span data-stu-id="b117a-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="b117a-103">Anstatt eine Linie mit einer Volltonfarbe, können Sie eine Zeile mit einer Textur zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b117a-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="b117a-104">Zum Zeichnen von Linien und Kurven mit einer Textur erstellen Sie eine <xref:System.Drawing.TextureBrush> Objekt, und übergeben, die <xref:System.Drawing.TextureBrush> -Objekt an eine <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b117a-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="b117a-105">Die Bitmap der Texturpinsel zugeordneten wird verwendet, um die Kachel "die Ebene (Hintergrund)", und wenn der Stift über ein Linien- oder Kurvensegmente zeichnet, wird der Strich des Stifts ereignisverarbeitungsmodul bestimmte Pixel gekachelt.</span><span class="sxs-lookup"><span data-stu-id="b117a-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b117a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b117a-106">Example</span></span>  
 <span data-ttu-id="b117a-107">Das folgende Beispiel erstellt eine <xref:System.Drawing.Bitmap> Objekt aus der Datei `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="b117a-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="b117a-108">Diese Bitmap wird zum Erstellen einer <xref:System.Drawing.TextureBrush> -Objekt, und die <xref:System.Drawing.TextureBrush> Objekt dient zum Erstellen einer <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="b117a-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b117a-109">Der Aufruf von <xref:System.Drawing.Graphics.DrawImage%2A> zeichnet die Bitmap mit der linken oberen Ecke auf (0, 0).</span><span class="sxs-lookup"><span data-stu-id="b117a-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="b117a-110">Der Aufruf von <xref:System.Drawing.Graphics.DrawEllipse%2A> verwendet die <xref:System.Drawing.Pen> Objekt, das eine strukturierte Ellipse gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b117a-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="b117a-111">Die folgende Abbildung zeigt die Bitmap und der texturierten Ellipse:</span><span class="sxs-lookup"><span data-stu-id="b117a-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![Screenshot mit der Bitmap und der texturierten Ellipse.](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b117a-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b117a-113">Compiling the Code</span></span>  
 <span data-ttu-id="b117a-114">Erstellen Sie ein Windows Form und behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b117a-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="b117a-115">Fügen Sie den vorherigen Code in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b117a-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b117a-116">Ersetzen Sie dies `Texture.jpg` mit einem Bild auf Ihrem System ungültig.</span><span class="sxs-lookup"><span data-stu-id="b117a-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b117a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b117a-117">See also</span></span>

- [<span data-ttu-id="b117a-118">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="b117a-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="b117a-119">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b117a-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
