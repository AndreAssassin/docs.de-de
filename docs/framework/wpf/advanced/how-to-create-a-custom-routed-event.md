---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: a3850875c8ca747f8709b55f8fe721d25be24304
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776687"
---
# <a name="how-to-create-a-custom-routed-event"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses
Für das benutzerdefinierte Ereignis zur Unterstützung von Ereignisrouting, müssen Sie registrieren einen <xref:System.Windows.RoutedEvent> mithilfe der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> Methode. Dieses Beispiel zeigt die Grundlagen der Erstellung eines benutzerdefinierten Routingereignisses.  
  
## <a name="example"></a>Beispiel  
 Wie im folgenden Beispiel gezeigt, registrieren Sie zuerst eine <xref:System.Windows.RoutedEvent> mithilfe der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> Methode. Gemäß der Konvention der <xref:System.Windows.RoutedEvent> statische Feldname muss mit der Endung ***Ereignis***. In diesem Beispiel ist der Name des Ereignisses ist `Tap` und die Routingstrategie des Ereignisses ist <xref:System.Windows.RoutingStrategy.Bubble>. Nach dem Registrierungsaufruf können Sie Ereignisaccessoren [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] für das Ereignis bereitstellen, hinzufügen und entfernen.  
  
 Beachten Sie, dass die Art, obwohl das Ereignis in diesem speziellen Beispiel über die virtuelle Methode `OnTap` ausgelöst wird, wie Sie das Ereignis auslösen oder wie Ihr Event auf Änderungen reagiert, von Ihren Anforderungen abhängt.  
  
 Beachten Sie, dass dieses Beispiel im Grunde eine gesamte Unterklasse von implementiert <xref:System.Windows.Controls.Button>; diese Unterklasse wird als separate Assembly erstellt und dann instanziiert, wie eine benutzerdefinierte Klasse auf einem separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite. Dadurch wird veranschaulicht, dass Steuerelemente als Unterklasse in Strukturen, die aus anderen Steuerelementen zusammengesetzt sind, eingefügt werden können, und in diesem Fall benutzerdefinierte Ereignisse dieser Steuerelemente über die gleichen Ereignisroutingfunktionen wie jedes native Element von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügen.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Tunneling-Ereignisse werden mit dem erstellt, viel, aber mit <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> festgelegt <xref:System.Windows.RoutingStrategy.Tunnel> im Registrierungsaufruf. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erhalten Tunneling-Ereignissen per Konvention das Wort „Preview“ als Präfix.  
  
 Ein Beispiel der Funktionsweise des Bubbling von Ereignissen finden Sie unter [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
