---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Bereichselements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: d4fc9d76ada9f27bd52619280b323691af9382c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139567"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="fa5f4-102">Vorgehensweise: Erstellen eines benutzerdefinierten Bereichselements</span><span class="sxs-lookup"><span data-stu-id="fa5f4-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="fa5f4-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa5f4-103">Example</span></span>  
 <span data-ttu-id="fa5f4-104">In diesem Beispiel wird veranschaulicht, das das Standardverhalten des Layouts des überschreiben die <xref:System.Windows.Controls.Panel> Element, und erstellen Sie benutzerdefinierte Layouts-Elemente, die abgeleitet sind <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="fa5f4-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="fa5f4-105">Im Beispiel definiert eine einfache benutzerdefinierte <xref:System.Windows.Controls.Panel> Element namens `PlotPanel`, die untergeordneten Elemente zwei hartcodierten x und y-Koordinaten entsprechend positioniert.</span><span class="sxs-lookup"><span data-stu-id="fa5f4-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="fa5f4-106">In diesem Beispiel `x` und `y` auf festlegen `50`; aus diesem Grund werden alle untergeordneten Elemente an diesem Speicherort auf der x- und y positioniert Achsen.</span><span class="sxs-lookup"><span data-stu-id="fa5f4-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="fa5f4-107">Zum Implementieren von benutzerdefinierten <xref:System.Windows.Controls.Panel> Verhalten, das Beispiel verwendet die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="fa5f4-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="fa5f4-108">Jede Methode gibt die <xref:System.Windows.Size> Daten, die zum Positionieren und die untergeordneten Elemente gerendert sind.</span><span class="sxs-lookup"><span data-stu-id="fa5f4-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fa5f4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa5f4-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="fa5f4-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="fa5f4-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="fa5f4-111">Erstellen einer benutzerdefinierten Content-Wrapping Panel Sample</span><span class="sxs-lookup"><span data-stu-id="fa5f4-111">Create a Custom Content-Wrapping Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159979)
