---
title: 'Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: a719381863d560a5666c7fc1a5e7260a1d4c4823
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650899"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="88b7e-102">Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="88b7e-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="88b7e-103">Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben.</span><span class="sxs-lookup"><span data-stu-id="88b7e-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="88b7e-104">Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert.</span><span class="sxs-lookup"><span data-stu-id="88b7e-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="88b7e-105">Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert.</span><span class="sxs-lookup"><span data-stu-id="88b7e-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="88b7e-106">Da auf dem Bildschirm nur eine Grafikoperation ausgeführt wird, wird die durch komplexe Zeichenoperationen ausgelöste Bildflimmern beseitigt. Für die meisten Anwendungen, die von bereitgestellten standardmäßige doppelte Pufferung der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bieten die besten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="88b7e-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="88b7e-107">Standardmäßigen Windows Forms-Steuerelemente sind doppelte standardmäßig gepuffert.</span><span class="sxs-lookup"><span data-stu-id="88b7e-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="88b7e-108">Sie können standardmäßige doppelte Pufferung in Ihren Formularen und Steuerelementen auf zwei Arten erstellt.</span><span class="sxs-lookup"><span data-stu-id="88b7e-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="88b7e-109">Können Sie entweder die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true`, oder Sie rufen die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag auf `true`.</span><span class="sxs-lookup"><span data-stu-id="88b7e-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="88b7e-110">Beide Methoden werden standardmäßige doppelte Pufferung für das Formular oder Steuerelement zu aktivieren und Bereitstellen flimmerfreier Grafik-Rendering.</span><span class="sxs-lookup"><span data-stu-id="88b7e-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="88b7e-111">Aufrufen der <xref:System.Windows.Forms.Control.SetStyle%2A> Methode wird empfohlen, nur für benutzerdefinierte Steuerelemente, die für die Sie alle wiedergebenden Code geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="88b7e-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="88b7e-112">Für erweiterte Szenarien mit doppelter Pufferung, wie Animationen oder erweiterter Speicherverwaltung können Sie Ihre eigene doppelte Pufferung Logik implementieren.</span><span class="sxs-lookup"><span data-stu-id="88b7e-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="88b7e-113">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="88b7e-113">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="88b7e-114">Um Flimmern zu verringern</span><span class="sxs-lookup"><span data-stu-id="88b7e-114">To reduce flicker</span></span>  
  
- <span data-ttu-id="88b7e-115">Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="88b7e-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="88b7e-116">\- oder –</span><span class="sxs-lookup"><span data-stu-id="88b7e-116">\- or -</span></span>  
  
- <span data-ttu-id="88b7e-117">Rufen Sie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag `true`.</span><span class="sxs-lookup"><span data-stu-id="88b7e-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="88b7e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88b7e-118">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="88b7e-119">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="88b7e-119">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="88b7e-120">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88b7e-120">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
