---
title: Verwenden eines Stiftes zum Zeichnen von Linien und Formen
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: d20b4e47c9f8a5dd7a144e6ebb3151d3ab65a800
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505138"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="d4452-102">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="d4452-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="d4452-103">Verwenden von GDI + `Pen` Objekte Liniensegmente, Kurven und Umrisse von Formen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d4452-103">Use GDI+ `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="d4452-104">In diesem Abschnitt *Zeile* verweist auf diese, sofern angegeben, um ein Liniensegment bedeuten.</span><span class="sxs-lookup"><span data-stu-id="d4452-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="d4452-105">Festlegen der Eigenschaften eines Stifts zum Steuern von Farbe, Breite, Ausrichtung und Stil der mit diesem Stift gezeichneten Linien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4452-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4452-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d4452-106">In This Section</span></span>  
 [<span data-ttu-id="d4452-107">Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Linien</span><span class="sxs-lookup"><span data-stu-id="d4452-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="d4452-108">Erläutert, wie zum Zeichnen von Linien.</span><span class="sxs-lookup"><span data-stu-id="d4452-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="d4452-109">Vorgehensweise: Verwenden eines Stiftes zum Zeichnen von Rechtecken</span><span class="sxs-lookup"><span data-stu-id="d4452-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="d4452-110">Beschreibt, wie zum Zeichnen von Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="d4452-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="d4452-111">Vorgehensweise: Festlegen von Stiftbreite und-Ausrichtung</span><span class="sxs-lookup"><span data-stu-id="d4452-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="d4452-112">Erläutert, wie die Breite und Ausrichtung ändern eine `Pen` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d4452-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="d4452-113">Vorgehensweise: Zeichnen einer Linie mit Linienenden</span><span class="sxs-lookup"><span data-stu-id="d4452-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="d4452-114">Beschreibt, wie Linienenden hinzugefügt werden soll, wenn eine Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d4452-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="d4452-115">Vorgehensweise: Verknüpfen von Linien</span><span class="sxs-lookup"><span data-stu-id="d4452-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="d4452-116">Zeigt, wie zum Verbinden von zwei Linien.</span><span class="sxs-lookup"><span data-stu-id="d4452-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="d4452-117">Vorgehensweise: Zeichnen einer benutzerdefinierten gestrichelten Linie</span><span class="sxs-lookup"><span data-stu-id="d4452-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="d4452-118">Beschreibt, wie eine gestrichelte Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d4452-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="d4452-119">Vorgehensweise: Zeichnen einer mit einer Textur ausgefüllten Linie</span><span class="sxs-lookup"><span data-stu-id="d4452-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="d4452-120">Es wird erläutert, wie eine Textur ausgefüllten Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d4452-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4452-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="d4452-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="d4452-122">Beschreibt diese Klasse und enthält Links zu allen deren Membern.</span><span class="sxs-lookup"><span data-stu-id="d4452-122">Describes this class and has links to all its members.</span></span>
