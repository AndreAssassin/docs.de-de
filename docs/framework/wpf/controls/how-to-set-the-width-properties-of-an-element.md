---
title: 'Vorgehensweise: Festlegen der Breiteneigenschaften eines Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: a5ed67ba20176398a863a1e9826b1eab71b182f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096874"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="e7443-102">Vorgehensweise: Festlegen der Breiteneigenschaften eines Elements</span><span class="sxs-lookup"><span data-stu-id="e7443-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="e7443-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7443-103">Example</span></span>  
 <span data-ttu-id="e7443-104">Dieses Beispiel zeigt die Unterschiede im Renderingverhalten zwischen den vier Breite-bezogene Eigenschaften im, visuell [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7443-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="e7443-105">Die <xref:System.Windows.FrameworkElement> Klasse stellt vier Eigenschaften, die die Breiteneigenschaften eines Elements zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e7443-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="e7443-106">Diese vier Eigenschaften können zu Konflikten führen, und wenn dies der Fall, wird der Wert, der Vorrang wie folgt bestimmt: die <xref:System.Windows.FrameworkElement.MinWidth%2A> Wert hat Vorrang vor den <xref:System.Windows.FrameworkElement.MaxWidth%2A> -Wert, der wiederum Vorrang vor den <xref:System.Windows.FrameworkElement.Width%2A> Wert.</span><span class="sxs-lookup"><span data-stu-id="e7443-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="e7443-107">Vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualWidth%2A>ist schreibgeschützt und gibt die tatsächliche Breite von Interaktionen mit der Layoutvorgang bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e7443-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="e7443-108">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispielen wird eine <xref:System.Windows.Shapes.Rectangle> Element (`rect1`) als untergeordnetes Element des <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e7443-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e7443-109">Sie können die Breiteneigenschaften ändern eine <xref:System.Windows.Shapes.Rectangle> mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox> Elemente, die die Eigenschaftswerte darstellen <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, und <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7443-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="e7443-110">Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7443-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="e7443-111">Die Ereignisse behandeln, in den folgenden Code-Behind-Beispielen, die die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="e7443-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="e7443-112">Jede benutzerdefinierte Methode übernimmt die Eingabe von der <xref:System.Windows.Controls.ListBox>, analysiert den Wert als eine <xref:System.Double>, und der Wert der angegebenen Breite bezogene-Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="e7443-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="e7443-113">Die Width-Werte sind auch in eine Zeichenfolge konvertiert und in verschiedenen geschrieben <xref:System.Windows.Controls.TextBlock> Elemente (die Definition dieser Elemente wird in der ausgewählten XAML nicht angezeigt).</span><span class="sxs-lookup"><span data-stu-id="e7443-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="e7443-114">Das vollständige Beispiel finden Sie unter [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span><span class="sxs-lookup"><span data-stu-id="e7443-114">For the complete sample, see [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7443-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7443-115">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="e7443-116">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="e7443-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e7443-117">Festlegen der Höheneigenschaften eines Elements</span><span class="sxs-lookup"><span data-stu-id="e7443-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="e7443-118">Width Properties Comparison Sample</span><span class="sxs-lookup"><span data-stu-id="e7443-118">Width Properties Comparison Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160050)
