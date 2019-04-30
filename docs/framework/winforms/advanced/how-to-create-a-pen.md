---
title: 'Vorgehensweise: Erstellen eines Stifts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 69fe6157c710ae63df9dbf391a5d355d1c3f9765
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004405"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="66254-102">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="66254-102">How to: Create a Pen</span></span>
<span data-ttu-id="66254-103">In diesem Beispiel wird eine <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="66254-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66254-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66254-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="66254-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="66254-105">Robust Programming</span></span>  
 <span data-ttu-id="66254-106">Nach dem Verwenden von Objekten, die Systemressourcen, z. B. nutzen <xref:System.Drawing.Pen> Objekte, rufen Sie <xref:System.Drawing.Pen.Dispose%2A> darauf.</span><span class="sxs-lookup"><span data-stu-id="66254-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66254-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66254-107">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="66254-108">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="66254-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="66254-109">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="66254-109">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
