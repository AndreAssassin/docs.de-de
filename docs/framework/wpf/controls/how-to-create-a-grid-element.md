---
title: 'Vorgehensweise: Erstellen eines Rasterelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: ebb9369da73bd595338e5b6ef42bda639bde6ed4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134536"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="9d023-102">Vorgehensweise: Erstellen eines Rasterelements</span><span class="sxs-lookup"><span data-stu-id="9d023-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="9d023-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d023-103">Example</span></span>  
 <span data-ttu-id="9d023-104">Das folgende Beispiel zeigt das Erstellen und verwenden Sie eine Instanz des <xref:System.Windows.Controls.Grid> entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code.</span><span class="sxs-lookup"><span data-stu-id="9d023-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="9d023-105">In diesem Beispiel verwendet drei <xref:System.Windows.Controls.ColumnDefinition> Objekte und drei <xref:System.Windows.Controls.RowDefinition> Objekte zum Erstellen eines Rasters, das neun Zellen, z. B. in einem Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="9d023-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="9d023-106">Jede Zelle enthält einen <xref:System.Windows.Controls.TextBlock> Element, das darstellt, Daten, und die oberste Zeile enthält einen <xref:System.Windows.Controls.TextBlock> mit der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d023-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="9d023-107">Zum Anzeigen der Grenzen jeder Zelle, die <xref:System.Windows.Controls.Grid.ShowGridLines%2A> -Eigenschaft aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d023-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="9d023-108">Beide Vorgehensweisen generiert eine Benutzeroberfläche, die viel identisch, wie folgt aussieht.</span><span class="sxs-lookup"><span data-stu-id="9d023-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![ein Screenshot zeigt eine WPF-Benutzeroberfläche enthält ein Raster in drei Spalten unterteilt ist.](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="9d023-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d023-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="9d023-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="9d023-113">Panels Overview</span></span>](panels-overview.md)
