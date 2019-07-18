---
title: 'Vorgehensweise: Behandeln eines geladenen Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: b8cd2f5e9d848cebb712e7b4930ca39efe48ecc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122550"
---
# <a name="how-to-handle-a-loaded-event"></a>Vorgehensweise: Behandeln eines geladenen Ereignisses
Dieses Beispiel zeigt, wie behandelt die <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> Ereignis und einem entsprechenden Szenario für die Behandlung dieses Ereignisses. Der Ereignishandler erstellt ein <xref:System.Windows.Controls.Button> beim Laden der Seite.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zusammen mit einem Code-Behind-Datei.  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement>
- [Objektlebensdauer-Ereignisse](object-lifetime-events.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Themen zu Vorgehensweisen](base-elements-how-to-topics.md)
