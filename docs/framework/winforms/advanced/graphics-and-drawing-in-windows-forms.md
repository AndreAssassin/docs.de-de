---
title: Grafik und Zeichnen in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938176"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="1f6bc-102">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f6bc-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="1f6bc-103">Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows-Grafikdesignoberfläche ([!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]), die so genannte [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f6bc-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="1f6bc-104">Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="1f6bc-105">vereint Leistung und Komfort.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-105">is designed to offer performance and ease of use.</span></span> <span data-ttu-id="1f6bc-106">Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] lassen sich grafische Bilder in Windows Forms und Steuerelementen rendern.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="1f6bc-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann zwar in Web Forms nicht direkt verwendet werden, jedoch können Sie grafische Bilder mit dem Image-Webserversteuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="1f6bc-108">Dieser Abschnitt enthält Themen, die Sie in die Grundlagen der Programmierung mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] einführen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="1f6bc-109">Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="1f6bc-110">Weitere Informationen finden Sie unter [GDI + Verweis](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="1f6bc-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="1f6bc-111">Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="1f6bc-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="1f6bc-112">Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f6bc-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1f6bc-113">In This Section</span></span>  
 [<span data-ttu-id="1f6bc-114">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="1f6bc-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="1f6bc-115">Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="1f6bc-116">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="1f6bc-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="1f6bc-117">Enthält Informationen zu den verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f6bc-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="1f6bc-118">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="1f6bc-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="1f6bc-119">Veranschaulicht die Ausführung verschiedener Aufgaben mithilfe der verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f6bc-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1f6bc-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="1f6bc-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="1f6bc-121">Ermöglicht den Zugriff auf die grundlegenden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="1f6bc-122">Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="1f6bc-123">Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Bildfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="1f6bc-124">Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Typografiefunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="1f6bc-125">Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="1f6bc-126">Stellt Druckfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f6bc-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1f6bc-127">Related Sections</span></span>  
 [<span data-ttu-id="1f6bc-128">Zeichnen und Rendern von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1f6bc-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="1f6bc-129">Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-129">Details how to provide code for painting controls.</span></span>
