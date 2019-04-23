---
title: 'Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204613"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt
Dieses Beispiel zeigt, wie Sie feststellen, ob die <xref:System.Windows.Input.Key.Enter> Taste auf der Tastatur gedrückt wird.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer drückt die <xref:System.Windows.Input.Key.Enter> -Schlüssel in der <xref:System.Windows.Controls.TextBox>, die Eingabe in das Textfeld angezeigt wird, in einem anderen Bereich von der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus einem <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, und ein <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.KeyDown> -Ereignishandler.  Wenn der Schlüssel, die gedrückt wird, wird die <xref:System.Windows.Input.Key.Enter> drücken, wird eine Meldung angezeigt, der <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
