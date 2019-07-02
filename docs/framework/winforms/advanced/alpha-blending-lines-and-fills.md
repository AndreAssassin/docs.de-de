---
title: Alphablending von Linien und Füllungen
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506121"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="b5987-102">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="b5987-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="b5987-103">In GDI + ist eine Farbe für einen 32-Bit-Wert, mit jeweils 8 Bit für den Alpha-, Rot-, Grün- und Blau.</span><span class="sxs-lookup"><span data-stu-id="b5987-103">In GDI+, a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="b5987-104">Der alpha-Wert gibt an, die Transparenz der Farbe, den Umfang, der die Farbe mit der Hintergrundfarbe vermischt wird.</span><span class="sxs-lookup"><span data-stu-id="b5987-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="b5987-105">Alpha-Werte-Bereich von 0 bis 255, wobei 0 für eine vollständig transparente Farbe darstellt, und 255 stellt eine vollständig deckende Farbe dar.</span><span class="sxs-lookup"><span data-stu-id="b5987-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="b5987-106">Alphablending ist eine x-Pixel-Kombination von der Quell- und Hintergrund Farbdaten.</span><span class="sxs-lookup"><span data-stu-id="b5987-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="b5987-107">Jede der drei Komponenten (Rot, Grün, Blau) eine Farbe für die angegebene Quelle wird mit der entsprechenden Komponente der Farbe des Hintergrunds, gemäß der folgenden Formel gemischt:</span><span class="sxs-lookup"><span data-stu-id="b5987-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="b5987-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span><span class="sxs-lookup"><span data-stu-id="b5987-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="b5987-109">Nehmen wir beispielsweise an der roten Anteil der Quellfarbe 150 und Rotanteils der Farbe des Hintergrunds ist 100.</span><span class="sxs-lookup"><span data-stu-id="b5987-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="b5987-110">Wenn der alpha-Wert 200 ist, wird Rotanteils der die resultierende Farbe wie folgt berechnet:</span><span class="sxs-lookup"><span data-stu-id="b5987-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="b5987-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="b5987-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5987-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b5987-112">In This Section</span></span>  
 [<span data-ttu-id="b5987-113">Vorgehensweise: Zeichnen Sie deckender und halbtransparente Linien</span><span class="sxs-lookup"><span data-stu-id="b5987-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="b5987-114">Veranschaulicht, wie Bereiche mit Alphablending von Linien zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="b5987-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="b5987-115">Vorgehensweise: Zeichnen Sie mit nicht transparenten und halb transparenten Pinseln</span><span class="sxs-lookup"><span data-stu-id="b5987-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="b5987-116">Alpha-Blend mit Pinseln erläutert.</span><span class="sxs-lookup"><span data-stu-id="b5987-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="b5987-117">Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings</span><span class="sxs-lookup"><span data-stu-id="b5987-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="b5987-118">Beschreibt, wie Sie steuern die Alphablending mit <xref:System.Drawing.Drawing2D.CompositingMode>.</span><span class="sxs-lookup"><span data-stu-id="b5987-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="b5987-119">Vorgehensweise: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern</span><span class="sxs-lookup"><span data-stu-id="b5987-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="b5987-120">Erläutert, wie eine <xref:System.Drawing.Imaging.ColorMatrix> Objekt zum Steuern des Alphablendings.</span><span class="sxs-lookup"><span data-stu-id="b5987-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
