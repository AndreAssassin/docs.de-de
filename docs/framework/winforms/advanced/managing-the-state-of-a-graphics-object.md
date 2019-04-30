---
title: Verwalten des Zustands eines Graphics-Objekts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: 8fc92bf84def50bed54a054ae634a8a08c8835c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936875"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="91351-102">Verwalten des Zustands eines Graphics-Objekts</span><span class="sxs-lookup"><span data-stu-id="91351-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="91351-103">Die <xref:System.Drawing.Graphics> -Klasse ist das Herzstück von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91351-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="91351-104">Um alles zu zeichnen, Sie erhalten eine <xref:System.Drawing.Graphics> Objekt, dessen Eigenschaften festlegen und seine Methoden aufrufen <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, usw.).</span><span class="sxs-lookup"><span data-stu-id="91351-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="91351-105">Im folgenden Beispiel wird die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91351-106">Das erste Argument zu übergeben, um die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode ist eine <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="91351-107">Grafikzustand</span><span class="sxs-lookup"><span data-stu-id="91351-107">Graphics State</span></span>  
 <span data-ttu-id="91351-108">Ein <xref:System.Drawing.Graphics> Objekt bietet mehr als Zeichenmethoden wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A> und <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="91351-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="91351-109">Ein <xref:System.Drawing.Graphics> -Objekt verwaltet auch den Grafikstatus, die in der folgenden Kategorien unterteilt werden können:</span><span class="sxs-lookup"><span data-stu-id="91351-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="91351-110">Einstellungen für die Qualität</span><span class="sxs-lookup"><span data-stu-id="91351-110">Quality settings</span></span>  
  
- <span data-ttu-id="91351-111">Transformationen</span><span class="sxs-lookup"><span data-stu-id="91351-111">Transformations</span></span>  
  
- <span data-ttu-id="91351-112">Ausschneidebereich</span><span class="sxs-lookup"><span data-stu-id="91351-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="91351-113">Einstellungen für die Qualität</span><span class="sxs-lookup"><span data-stu-id="91351-113">Quality Settings</span></span>  
 <span data-ttu-id="91351-114">Ein <xref:System.Drawing.Graphics> Objekt verfügt über mehrere Eigenschaften, die die Qualität der Elemente beeinflussen, die gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="91351-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="91351-115">Sie können z. B. Festlegen der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft, um den Typ des Antialiasing (sofern vorhanden), die auf einen Text angewendeten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91351-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="91351-116">Andere Eigenschaften, die Qualität beeinflussen sind <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, und <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="91351-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="91351-117">Im folgende Beispiel werden zwei Ellipsen mit den Glättungsmodus gezeichnet <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> und eine mit der Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="91351-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="91351-118">Transformationen</span><span class="sxs-lookup"><span data-stu-id="91351-118">Transformations</span></span>  
 <span data-ttu-id="91351-119">Ein <xref:System.Drawing.Graphics> -Objekt verwaltet zwei Transformationen ("World" und "Seite"), die für alle Elemente, die vom, die angewendet werden <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91351-120">Eine affine Transformation kann in der globalen Transformation gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="91351-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="91351-121">Affine Transformationen enthalten, skalieren, drehen, spiegeln, neigen und übersetzen.</span><span class="sxs-lookup"><span data-stu-id="91351-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="91351-122">Die Seitentransformation kann für die Skalierung sowie zum Ändern von Einheiten (z. B. Pixel, Zoll) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91351-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="91351-123">Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="91351-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="91351-124">Im folgenden Beispiel wird die Seite "und" World Transformationen von einem <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91351-125">Die globale Transformation wird auf eine 30-Grad-Drehung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="91351-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="91351-126">Die Seitentransformation wird festgelegt, sodass die Koordinaten für die zweite übergeben <xref:System.Drawing.Graphics.DrawEllipse%2A> als Millimeter anstelle von Pixel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="91351-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="91351-127">Der Code führt zwei identische Aufrufe der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="91351-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="91351-128">Die globale Transformation angewendet wird, mit dem ersten <xref:System.Drawing.Graphics.DrawEllipse%2A> Aufruf, und beide Transformationen ("World" und "Seite") gelten für die zweite <xref:System.Drawing.Graphics.DrawEllipse%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="91351-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="91351-129">Die folgende Abbildung zeigt zwei Ellipsen.</span><span class="sxs-lookup"><span data-stu-id="91351-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="91351-130">Beachten Sie, dass die 30-Grad-Drehung um den Ursprung des Koordinatensystems (linke obere Ecke des Clientbereichs), nicht jedoch zu den Mittelpunkten die Auslassungspunkte.</span><span class="sxs-lookup"><span data-stu-id="91351-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="91351-131">Beachten Sie außerdem, dass mit der die Stiftbreite 1 1-Pixel für die erste Ellipse und 1 mm für die zweite Ellipse.</span><span class="sxs-lookup"><span data-stu-id="91351-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Abbildung der zwei Ellipsen: Drehung und Stift-Breite.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="91351-133">Ausschneidebereich</span><span class="sxs-lookup"><span data-stu-id="91351-133">Clipping Region</span></span>  
 <span data-ttu-id="91351-134">Ein <xref:System.Drawing.Graphics> -Objekt verwaltet einen Ausschneidebereich, der für alle Elemente, die von diesem gilt <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91351-135">Sie können den Ausschneidebereich festlegen, durch den Aufruf der <xref:System.Drawing.Graphics.SetClip%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="91351-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="91351-136">Das folgende Beispiel erstellt eine Region Plus gestalteten durch Bildung der Union von zwei Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="91351-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="91351-137">Diese Region als der Ausschneidebereich festgelegt wurde eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="91351-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="91351-138">Der Code zeichnet dann zwei Zeilen, die auf das Innere des Clippingbereichs beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="91351-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="91351-139">Die folgende Abbildung zeigt die abgeschnittenen Zeilen:</span><span class="sxs-lookup"><span data-stu-id="91351-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Diagramm der beschränkter Clip-Bereich zeigt.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="91351-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91351-141">See also</span></span>

- [<span data-ttu-id="91351-142">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91351-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="91351-143">Verwenden geschachtelter Grafikcontainer</span><span class="sxs-lookup"><span data-stu-id="91351-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
