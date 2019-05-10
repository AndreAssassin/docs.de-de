---
title: 'Vorgehensweise: Auflisten installierter Decoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626906"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="5bb9d-102">Vorgehensweise: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="5bb9d-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="5bb9d-103">Möglicherweise möchten die Liste die auf einem Computer verfügbaren Bilddecoder, um festzustellen, ob Ihre Anwendung ein bestimmtes Bildformat Datei lesen kann.</span><span class="sxs-lookup"><span data-stu-id="5bb9d-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="5bb9d-104">Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> statische Methoden, damit Sie bestimmen können, welche Bilddecoder verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5bb9d-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="5bb9d-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="5bb9d-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bb9d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bb9d-106">Example</span></span>  
 <span data-ttu-id="5bb9d-107">Das folgende Codebeispiel gibt die Liste der installierten Decoder und zugehörigen Eigenschaftswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="5bb9d-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5bb9d-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5bb9d-108">Compiling the Code</span></span>  
 <span data-ttu-id="5bb9d-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5bb9d-109">This example requires:</span></span>  
  
- <span data-ttu-id="5bb9d-110">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5bb9d-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="5bb9d-111">Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5bb9d-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb9d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bb9d-112">See also</span></span>

- [<span data-ttu-id="5bb9d-113">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="5bb9d-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="5bb9d-114">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="5bb9d-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
