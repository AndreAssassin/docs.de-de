---
title: 'Vorgehensweise: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView-Objekt'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145404"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Vorgehensweise: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView-Objekt
In diesem Beispiel wird gezeigt, wie definiert <xref:System.Windows.Style.Triggers%2A> für eine <xref:System.Windows.Controls.ListViewItem> Steuerelement, damit Wenn ein Eigenschaftswert, der eine <xref:System.Windows.Controls.ListViewItem> Änderungen, die <xref:System.Windows.Style> von der <xref:System.Windows.Controls.ListViewItem> Änderungen als Reaktion.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie möchten die <xref:System.Windows.Style> von eine <xref:System.Windows.Controls.ListViewItem> definieren, um als Reaktion auf Änderungen der Eigenschaften zu ändern, <xref:System.Windows.Style.Triggers%2A> für die <xref:System.Windows.Style> ändern.  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.Trigger> , der festlegt der <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft, um <xref:System.Windows.Media.Brushes.Blue%2A> und ändert die <xref:System.Windows.FrameworkElement.Cursor%2A> anzuzeigende eine <xref:System.Windows.Input.CursorType.Hand> beim der <xref:System.Windows.UIElement.IsMouseOver%2A> eigenschaftsänderungen `true`.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.MultiTrigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft eine <xref:System.Windows.Controls.ListViewItem> zu <xref:System.Windows.Media.Brushes.Yellow%2A> beim der <xref:System.Windows.Controls.ListViewItem> das ausgewählte Element und hat den Tastaturfokus.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Gewusst wie-Themen](listview-how-to-topics.md)
- [Übersicht über ListView](listview-overview.md)
- [Übersicht über GridView](gridview-overview.md)
