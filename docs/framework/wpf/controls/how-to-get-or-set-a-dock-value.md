---
title: 'Vorgehensweise: Abrufen oder Festlegen eines Dockwerts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160733"
---
# <a name="how-to-get-or-set-a-dock-value"></a>Vorgehensweise: Abrufen oder Festlegen eines Dockwerts
Das folgende Beispiel zeigt das Zuweisen einer <xref:System.Windows.Controls.Dock> Wert für ein Objekt. Im Beispiel wird die <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methoden <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Beispiel  
 Das Beispiel erstellt eine Instanz von der <xref:System.Windows.Controls.TextBlock> Element `txt1`, und weist eine <xref:System.Windows.Controls.Dock> Wert `Top` mithilfe der <xref:System.Windows.Controls.DockPanel.SetDock%2A> -Methode der <xref:System.Windows.Controls.DockPanel>. Anschließend fügt den Wert des der <xref:System.Windows.Controls.Dock> Eigenschaft, um die <xref:System.Windows.Controls.TextBlock.Text%2A> von der <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode. Zum Schluss das Beispiel fügt die <xref:System.Windows.Controls.TextBlock> Element, das dem übergeordneten <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [Übersicht über Panel-Elemente](panels-overview.md)
