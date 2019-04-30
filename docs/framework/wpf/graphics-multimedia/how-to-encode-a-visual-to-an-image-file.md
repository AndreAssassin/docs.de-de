---
title: 'Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 872c19af0cfcf4fc980643c37e9a6028457c03b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947575"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="d99a9-102">Vorgehensweise: Codieren eines Visual-Objekts in einer Bilddatei</span><span class="sxs-lookup"><span data-stu-id="d99a9-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="d99a9-103">In diesem Beispiel wird veranschaulicht, wie zum Codieren einer <xref:System.Windows.Media.Visual> Objekt in ein Bild mit einer <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="d99a9-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d99a9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d99a9-104">Example</span></span>  
 <span data-ttu-id="d99a9-105">Die <xref:System.Windows.Media.DrawingVisual> wurde mit einem <xref:System.Windows.Media.Imaging.BitmapImage> und <xref:System.Windows.Media.FormattedText> die gerendert wird, um eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="d99a9-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="d99a9-106">Die gerenderte Bitmap wird dann zum Erstellen einer <xref:System.Windows.Media.Imaging.BitmapFrame> hinzugefügt wird und auf die <xref:System.Windows.Media.Imaging.PngBitmapEncoder> zum Erstellen eines neuen [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] Datei.</span><span class="sxs-lookup"><span data-stu-id="d99a9-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="d99a9-107">Ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder> verwendet wurde, in diesem Beispiel jedoch eine der abgeleiteten <xref:System.Windows.Media.Imaging.BitmapEncoder> Objekte hätten verwendet werden können, erstellen Sie die Image-Datei.</span><span class="sxs-lookup"><span data-stu-id="d99a9-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99a9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d99a9-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="d99a9-109">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="d99a9-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="d99a9-110">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="d99a9-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d99a9-111">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="d99a9-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
