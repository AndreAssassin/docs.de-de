---
ms.openlocfilehash: 88e00454894c8404fd48e92404e35ae27fa056f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235223"
---
### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>WPF TreeViewItem muss in einem TreeView-Steuerelement verwendet werden

|   |   |
|---|---|
|Details|In .NET Framework 4.5 wurde eine Änderung eingeführt, die die Verwendung von <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>-Elementen außerhalb eines <xref:System.Windows.Controls.TreeView?displayProperty=name>-Steuerelements einschränkt. Dieser Fall kann unter den folgenden Bedingungen eintreten:<ul><li>Das visuelle übergeordnete Element von <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> ist kein Panel. (Ein für <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> generiertes <xref:System.Windows.Controls.TreeView?displayProperty=name>-Steuerelement weist einen Panel als dessen übergeordnetes Element auf.)</li><li>Das <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>-Element ist ein Nachfolgeelement von <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name>, das als &quot;Elementhost&quot; für ein Listensteuerelement (ListBox, DataGrid, ListView usw.) fungiert. Die Virtualisierung muss nicht aktiviert werden.</li><li>Das <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name>-Element wird zum Elementscrolling (<code>ScrollUnit=&quot;Item&quot;</code>) verwendet.</li><li>Jemand ruft <code>VirtualizingStackPanel.MakeVisible(v)</code> auf, um ein Element <code>v</code> in eine Ansicht zu scrollen. Dies kann auf verschiedene Arten explizit oder implizit erfolgen. Die am häufigsten verwendeten Methode ist möglicherweise einfach das Klicken auf <code>v</code>, damit es den Tastaturfokus erhält.</li><li>Die visuelle Kette des übergeordneten <code>v</code>-Elements zu <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> wird über das <xref:System.Windows.Controls.TreeViewItem?displayProperty=name>-Element übergeben.</li></ul>Das bedeutet, dies wird angezeigt, wenn ein <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> außerhalb von <xref:System.Windows.Controls.TreeView?displayProperty=name> verwendet wird und der Benutzer auf ein Nachfolgeelement von <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> klickt, um ihn anzuzeigen. Wenn <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> keine Nachfolgeelemente besitzt, die den Fokus erhalten können, tritt dieses Problem nicht auf. Ein Beispiel für eine entsprechende Situation liegt vor, wenn <xref:System.Windows.Controls.TreeViewItem?displayProperty=name> der Stamm von DataTemplate ist. Wenn dieses Problem erreicht wird, tritt „InvalidCastException“ innerhalb des WPF-Frameworks auf.|
|Vorschlag|Hierfür wird ein Hotfix zur Verfügung gestellt.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
