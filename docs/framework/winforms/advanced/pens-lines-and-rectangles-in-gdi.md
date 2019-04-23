---
title: Stifte, Linien und Rechtecke in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 84752773c0b56d9684dc31620d463d4ddccf9dad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078225"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="d7dc3-102">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="d7dc3-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="d7dc3-103">Zum Zeichnen von Linien mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] müssen Sie erstellen eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d7dc3-104">Die <xref:System.Drawing.Graphics> Objekt bietet Methoden, die den Zeichenvorgang, ausführen und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Farbe, Breite und Stil.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="d7dc3-105">Zeichnen einer Linie</span><span class="sxs-lookup"><span data-stu-id="d7dc3-105">Drawing a Line</span></span>  
 <span data-ttu-id="d7dc3-106">Um eine Linie zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="d7dc3-107">Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawLine%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="d7dc3-108">Im folgende Beispiel zeichnet eine Linie von der Punkt ("4", "2"), zu dem Punkt ("12", "6"):</span><span class="sxs-lookup"><span data-stu-id="d7dc3-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="d7dc3-109"><xref:System.Drawing.Graphics.DrawLine%2A> ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="d7dc3-110">Sie können z. B. erstellen zwei <xref:System.Drawing.Point> Objekte und übergeben Sie die <xref:System.Drawing.Point> -Objekte als Argumente an die <xref:System.Drawing.Graphics.DrawLine%2A> Methode:</span><span class="sxs-lookup"><span data-stu-id="d7dc3-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="d7dc3-111">Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="d7dc3-111">Constructing a Pen</span></span>  
 <span data-ttu-id="d7dc3-112">Sie können bestimmte Attribute angeben, beim Erstellen einer <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d7dc3-113">Z. B. eine `Pen` Konstruktor ermöglicht das Angeben von Farbe und Breite.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="d7dc3-114">Das folgende Beispiel zeichnet eine blaue Linie der Stärke von 2 aus (0, 0), (60, 30):</span><span class="sxs-lookup"><span data-stu-id="d7dc3-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="d7dc3-115">Gestrichelte Linien und Linienenden</span><span class="sxs-lookup"><span data-stu-id="d7dc3-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="d7dc3-116">Die <xref:System.Drawing.Pen> Objekt macht auch Eigenschaften, z. B. <xref:System.Drawing.Pen.DashStyle%2A>, dass Sie angeben, die Funktionen der Zeile verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="d7dc3-117">Das folgende Beispiel zeichnet eine gestrichelte Linie von (100, 50), (300, 80):</span><span class="sxs-lookup"><span data-stu-id="d7dc3-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="d7dc3-118">Können Sie die Eigenschaften der <xref:System.Drawing.Pen> Objekt, das die Zeile zahlreicher weiterer Attribute festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="d7dc3-119">Die <xref:System.Drawing.Pen.StartCap%2A> und <xref:System.Drawing.Pen.EndCap%2A> Eigenschaften angeben, die Darstellung der Enden der Linie, die Enden können Flatfile, Square, gerundet, dreieckig, oder eine benutzerdefinierte Form.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="d7dc3-120">Die <xref:System.Drawing.Pen.LineJoin%2A> -Eigenschaft können Sie angeben, ob miteinander verbundenen Linien Gehrung (verknüpft mit Ecken), abgeschrägt, gerundet oder abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="d7dc3-121">Die folgende Abbildung zeigt die Zeilen mit verschiedenen Arten von Cap und Join.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="d7dc3-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="d7dc3-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="d7dc3-123">Zeichnen eines Rechtecks</span><span class="sxs-lookup"><span data-stu-id="d7dc3-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="d7dc3-124">Zeichnen von Rechtecken in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ähnelt dem Zeichnen von Linien.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="d7dc3-125">Um ein Rechteck zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d7dc3-126">Die <xref:System.Drawing.Graphics> -Objekt ermöglicht eine <xref:System.Drawing.Graphics.DrawRectangle%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Linienstärke und Farbe.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="d7dc3-127">Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="d7dc3-128">Im folgende Beispiel zeichnet ein Rechteck mit der linken oberen Ecke an (100, 50), einer Breite von 80 und einer Höhe von 40:</span><span class="sxs-lookup"><span data-stu-id="d7dc3-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="d7dc3-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="d7dc3-130">Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> Objekt, und übergeben die <xref:System.Drawing.Rectangle> -Objekt an die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode als Argument:</span><span class="sxs-lookup"><span data-stu-id="d7dc3-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="d7dc3-131">Ein <xref:System.Drawing.Rectangle> Objekt enthält Methoden und Eigenschaften zum Bearbeiten und Sammeln von Informationen über das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="d7dc3-132">Z. B. die <xref:System.Drawing.Rectangle.Inflate%2A> und <xref:System.Drawing.Rectangle.Offset%2A> Methoden ändern die Größe und Position des Rechtecks.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="d7dc3-133">Die <xref:System.Drawing.Rectangle.IntersectsWith%2A> Methode erfahren Sie, ob das Rechteck für einen anderen überschneidet angegebenen Rechteck, und die <xref:System.Drawing.Rectangle.Contains%2A> Methode erfahren Sie, ob ein bestimmter Punkt innerhalb des Rechtecks befindet.</span><span class="sxs-lookup"><span data-stu-id="d7dc3-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dc3-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7dc3-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="d7dc3-135">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="d7dc3-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="d7dc3-136">Vorgehensweise: Zeichnen einer Linie in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7dc3-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="d7dc3-137">Vorgehensweise: Zeichnen der Kontur eine Form</span><span class="sxs-lookup"><span data-stu-id="d7dc3-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
