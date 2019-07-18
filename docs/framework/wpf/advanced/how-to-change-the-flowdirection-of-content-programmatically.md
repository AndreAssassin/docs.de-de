---
title: 'Vorgehensweise: Programmgesteuertes Ändern der FlowDirection des Inhalts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776557"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Vorgehensweise: Programmgesteuertes Ändern der FlowDirection des Inhalts
Dieses Beispiel zeigt, wie Sie programmgesteuert ändern der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft eine <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Beispiel  
 Zwei <xref:System.Windows.Controls.Button> Elemente erstellt werden, jeweils eine der möglichen Werte des <xref:System.Windows.FlowDirection>. Wenn eine Schaltfläche geklickt wird, wird der zugehörige Eigenschaftswert auf den Inhalt angewendet eine <xref:System.Windows.Controls.FlowDocumentReader> mit dem Namen `tf1`.  Den Wert der Eigenschaft werden auch in geschrieben eine <xref:System.Windows.Controls.TextBlock> mit dem Namen `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Beispiel  
 Die Ereignisse im Zusammenhang mit den oben definierten Klicks auf Schaltflächen werden verarbeitet, einem C# Code-Behind-Datei.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
