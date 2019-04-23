---
title: 'Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145079"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Vorgehensweise: Behandeln des MouseDoubleClick-Ereignisses für die einzelnen ListView-Elemente
Behandeln eines Ereignisses für ein Element in einem <xref:System.Windows.Controls.ListView>, müssen Sie zum Hinzufügen eines ereignishandlers zu jeder <xref:System.Windows.Controls.ListViewItem>. Wenn eine <xref:System.Windows.Controls.ListView> gebunden ist Sie nicht explizit erstellen, mit einer Datenquelle eine <xref:System.Windows.Controls.ListViewItem>, aber Sie können das Ereignis für jedes Element behandeln, durch das Hinzufügen eine <xref:System.Windows.EventSetter> , einem Stil ein <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine datengebundene <xref:System.Windows.Controls.ListView> und erstellt eine <xref:System.Windows.Style> zum Hinzufügen eines ereignishandlers zu jeder <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Das folgende Beispiel verarbeitet die <xref:System.Windows.Controls.Control.MouseDoubleClick> Ereignis.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Obwohl es am häufigsten verwendeten gebunden ist, eine <xref:System.Windows.Controls.ListView> mit einer Datenquelle können Sie einen Stil verwenden, um einen Ereignishandler hinzuzufügen <xref:System.Windows.Controls.ListViewItem> in einer nicht-datengebundenen <xref:System.Windows.Controls.ListView> unabhängig davon, ob Sie explizit erstellen eine <xref:System.Windows.Controls.ListViewItem>.  Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem> Steuerelemente finden Sie <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlElement>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Übersicht über ListView](listview-overview.md)
