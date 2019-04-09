---
title: 'Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ae6ceb2ca3e541be1d7dd3e5a61a6e52b27e93c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152788"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="9a4a9-102">Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck</span><span class="sxs-lookup"><span data-stu-id="9a4a9-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="9a4a9-103">Sie können die umbrochenen Text in ein Rechteck zeichnen, mit der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, die von der <xref:System.Drawing.Graphics> Klasse, die akzeptiert eine <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF> Parameter.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="9a4a9-104">Sie können auch eine <xref:System.Drawing.Brush> und <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="9a4a9-105">Sie können auch umbrochenen Text in ein Rechteck zeichnen, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, die von der <xref:System.Windows.Forms.TextRenderer> , akzeptiert eine <xref:System.Drawing.Rectangle> und ein <xref:System.Windows.Forms.TextFormatFlags> Parameter.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="9a4a9-106">Sie können auch eine <xref:System.Drawing.Color> und <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="9a4a9-107">Die folgende Abbildung zeigt die Ausgabe von Text in das Rechteck gezeichnet werden, bei der Verwendung der <xref:System.Drawing.Graphics.DrawString%2A> Methode:</span><span class="sxs-lookup"><span data-stu-id="9a4a9-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![Screenshot, der die Ausgabe zeigt die Verwendung der Methode "DrawString".](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="9a4a9-109">Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI +</span><span class="sxs-lookup"><span data-stu-id="9a4a9-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="9a4a9-110">Verwenden der <xref:System.Drawing.Graphics.DrawString%2A> überladene Methode, und übergeben Sie den Text an, Sie möchten, <xref:System.Drawing.Rectangle> oder <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> und <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="9a4a9-111">Zum Zeichnen von umbrochenem Text in einem Rechteck mit GDI</span><span class="sxs-lookup"><span data-stu-id="9a4a9-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="9a4a9-112">Verwenden der <xref:System.Windows.Forms.TextFormatFlags> Enumerationswert zum Angeben des Texts eingebunden werden soll, mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> überladene Methode, und übergeben Sie den Text an, Sie möchten, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> und <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a4a9-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9a4a9-113">Compiling the Code</span></span>  
 <span data-ttu-id="9a4a9-114">Die vorherigen Beispiele erfordern Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a4a9-114">The previous examples require:</span></span>  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`<span data-ttu-id="9a4a9-115">, ein Parameter von <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9a4a9-115">, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a4a9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a4a9-116">See also</span></span>

- [<span data-ttu-id="9a4a9-117">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="9a4a9-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="9a4a9-118">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="9a4a9-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="9a4a9-119">Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="9a4a9-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="9a4a9-120">Vorgehensweise: Zeichnen von Text an einer angegebenen Position</span><span class="sxs-lookup"><span data-stu-id="9a4a9-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
