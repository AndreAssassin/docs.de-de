---
title: 'Vorgehensweise: Festlegen von Stiftbreite und -ausrichtung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605836"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="4cff2-102">Vorgehensweise: Festlegen von Stiftbreite und -ausrichtung</span><span class="sxs-lookup"><span data-stu-id="4cff2-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="4cff2-103">Bei der Erstellung einer <xref:System.Drawing.Pen>, Sie können die Stiftbreite als eines der Argumente an den Konstruktor bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4cff2-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="4cff2-104">Sie können auch die Stiftbreite mit Ändern der <xref:System.Drawing.Pen.Width%2A> Eigenschaft der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4cff2-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="4cff2-105">Eine theoretische Linie hat es sich um eine Breite von 0.</span><span class="sxs-lookup"><span data-stu-id="4cff2-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="4cff2-106">Wenn Sie eine Linie, die 1-Pixel breit ist zeichnen, werden die Pixel auf der theoretischen Linie zentriert.</span><span class="sxs-lookup"><span data-stu-id="4cff2-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="4cff2-107">Wenn Sie eine Linie, die mehr als einem Pixel Breite ist zeichnen, wird die Pixel werden entweder auf der theoretischen Linie zentriert oder werden auf einer Seite von der theoretischen Linie.</span><span class="sxs-lookup"><span data-stu-id="4cff2-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="4cff2-108">Sie können festlegen, die Stiftausrichtungseigenschaft, der eine <xref:System.Drawing.Pen> um zu bestimmen, wie die mit diesem Stift gezeichneten Pixel relativ zur theoretischen Linien positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="4cff2-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="4cff2-109">Die Werte <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, und <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , angezeigt werden, in der folgenden Codebeispiele sind Mitglieder der <xref:System.Drawing.Drawing2D.PenAlignment> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4cff2-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="4cff2-110">Im folgenden Codebeispiel wird zeichnet eine Linie zweimal: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.</span><span class="sxs-lookup"><span data-stu-id="4cff2-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="4cff2-111">Um die Breite des Stifts zu variieren.</span><span class="sxs-lookup"><span data-stu-id="4cff2-111">To vary the width of a pen</span></span>  
  
- <span data-ttu-id="4cff2-112">Legen Sie den Wert, der die <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> (Standard), um anzugeben, dass mit dem grünen Stift gezeichneten Pixel auf der theoretischen Linie zentriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4cff2-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="4cff2-113">Die folgende Abbildung zeigt die resultierende Linie.</span><span class="sxs-lookup"><span data-stu-id="4cff2-113">The following illustration shows the resulting line.</span></span>  
  
     ![Ein schwarzer thin Grün hervorgehobene Linie.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     <span data-ttu-id="4cff2-115">Im folgenden Codebeispiel wird zeichnet ein Rechteck zweimal: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.</span><span class="sxs-lookup"><span data-stu-id="4cff2-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="4cff2-116">So ändern Sie die Ausrichtung eines Stifts</span><span class="sxs-lookup"><span data-stu-id="4cff2-116">To change the alignment of a pen</span></span>  
  
- <span data-ttu-id="4cff2-117">Legen Sie den Wert von der <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> um anzugeben, dass die mit dem grünen Stift gezeichneten Pixel soll, auf die Begrenzung des Rechtecks zentriert werden.</span><span class="sxs-lookup"><span data-stu-id="4cff2-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="4cff2-118">Die folgende Abbildung zeigt das sich ergebende Rechteck:</span><span class="sxs-lookup"><span data-stu-id="4cff2-118">The following illustration shows the resulting rectangle:</span></span>
  
     ![Ein Rechteck mit dem schwarzen schmale Linien Grün hervorgehobene gezeichnet.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="4cff2-120">Ein abgesenkter Stift erstellen</span><span class="sxs-lookup"><span data-stu-id="4cff2-120">To create an inset pen</span></span>  
  
- <span data-ttu-id="4cff2-121">Ändern Sie den grünen Stift-Ausrichtung, indem Sie im obigen Codebeispiel wird die dritte Anweisung wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="4cff2-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="4cff2-122">Jetzt werden die Pixel in der breiten grünen Linie innerhalb des Rechtecks angezeigt, wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4cff2-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration:</span></span>
  
     ![Ein Rechteck mit schwarzen Linien mit der breiten grünen Linie in gezeichnet.](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a><span data-ttu-id="4cff2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cff2-124">See also</span></span>

- [<span data-ttu-id="4cff2-125">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="4cff2-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="4cff2-126">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cff2-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
