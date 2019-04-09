---
title: 'Vorgehensweise: Verknüpfen von Linien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 445d7f12f57137c6b06a074eeaf0574eb027a723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174914"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="94f00-102">Vorgehensweise: Verknüpfen von Linien</span><span class="sxs-lookup"><span data-stu-id="94f00-102">How to: Join Lines</span></span>
<span data-ttu-id="94f00-103">Ein Join für die Zeile ist die gemeinsamen Bereich, der zwei Zeilen gebildet wird, deren Enden erfüllen oder sich überlappen.</span><span class="sxs-lookup"><span data-stu-id="94f00-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="94f00-104">bietet drei: Linienverbindungsstile, Abschrägung und runden.</span><span class="sxs-lookup"><span data-stu-id="94f00-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="94f00-105">Linienverbindungsstil ist eine Eigenschaft der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="94f00-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="94f00-106">Wenn Sie einen Linienstil für die Verknüpfung für angeben einer <xref:System.Drawing.Pen> -Objekt, dass für alle verbundenen Linien in einem Join-Format angewendet wird <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt mit diesem Stift gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="94f00-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="94f00-107">Die folgende Abbildung zeigt die Ergebnisse des Beispiels Join abgeschrägte Zeile.</span><span class="sxs-lookup"><span data-stu-id="94f00-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![Abbildung der verknüpfte Zeilen.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="94f00-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94f00-109">Example</span></span>  
 <span data-ttu-id="94f00-110">Sie können die Linienart für den Join angeben, indem die <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="94f00-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="94f00-111">Das Beispiel zeigt eine abgeschrägte linienverbindung zwischen einer horizontalen Linie und eine vertikale Linie.</span><span class="sxs-lookup"><span data-stu-id="94f00-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="94f00-112">Im folgenden Code, den Wert <xref:System.Drawing.Drawing2D.LineJoin.Bevel> zugewiesen der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft ist ein Mitglied der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="94f00-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="94f00-113">Die anderen Mitglieder des der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration werden <xref:System.Drawing.Drawing2D.LineJoin.Miter> und <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="94f00-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94f00-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="94f00-114">Compiling the Code</span></span>  
 <span data-ttu-id="94f00-115">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="94f00-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f00-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94f00-116">See also</span></span>

- [<span data-ttu-id="94f00-117">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="94f00-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
