---
title: 'Vorgehensweise: Zeichnen von Text mit GDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3d5b79e82185c044314ff8807b86835ef6a87c45
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505911"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="966b1-102">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="966b1-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="966b1-103">Mit der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> -Methode in der die <xref:System.Windows.Forms.TextRenderer> -Klasse, können Sie GDI-Funktionen zum Zeichnen von Text in einem Formular oder Steuerelement zugreifen.</span><span class="sxs-lookup"><span data-stu-id="966b1-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="966b1-104">GDI-Text-Rendering stellt in der Regel eine bessere Leistung und genauere Text als GDI + messen.</span><span class="sxs-lookup"><span data-stu-id="966b1-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="966b1-105">Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methoden der <xref:System.Windows.Forms.TextRenderer> Klasse werden zum Drucken nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="966b1-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="966b1-106">Beim Drucken, verwenden Sie immer die <xref:System.Drawing.Graphics.DrawString%2A> Methoden der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="966b1-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="966b1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="966b1-107">Example</span></span>  
 <span data-ttu-id="966b1-108">Im folgenden Codebeispiel wird veranschaulicht, wie zum Zeichnen von Text auf mehrere Zeilen in einem Rechteck mithilfe der <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="966b1-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="966b1-109">Zum Rendern von Text mit der <xref:System.Windows.Forms.TextRenderer> -Klasse, die Sie benötigen ein <xref:System.Drawing.IDeviceContext>, z. B. eine <xref:System.Drawing.Graphics> und ein <xref:System.Drawing.Font>, einen Speicherort zum Zeichnen von Text und die Farbe, in denen es gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="966b1-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="966b1-110">Optional können Sie angeben, die textformatierung, die mithilfe der <xref:System.Windows.Forms.TextFormatFlags> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="966b1-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="966b1-111">Weitere Informationen zum Abrufen einer <xref:System.Drawing.Graphics>, finden Sie unter [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="966b1-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="966b1-112">Weitere Informationen zum Erstellen einer <xref:System.Drawing.Font>, finden Sie unter [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md).</span><span class="sxs-lookup"><span data-stu-id="966b1-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="966b1-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="966b1-113">Compiling the Code</span></span>  
 <span data-ttu-id="966b1-114">Das vorherige Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="966b1-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="966b1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="966b1-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="966b1-116">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="966b1-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
