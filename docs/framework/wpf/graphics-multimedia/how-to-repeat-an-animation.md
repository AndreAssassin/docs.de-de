---
title: 'Vorgehensweise: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942089"
---
# <a name="how-to-repeat-an-animation"></a>Vorgehensweise: Wiederholen einer Animation
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> um das Wiederholungsverhalten einer Animation steuern.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft eine Animation ihre einfache Dauer wiederholt. Mithilfe von <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, können Sie angeben, die eine <xref:System.Windows.Media.Animation.Timeline> für eine bestimmte Anzahl von Malen wiederholt (eine Iterationsanzahl) oder für einen bestimmten Zeitraum. In beiden Fällen durchläuft die Animation so viele Anfang-to-End ausgeführt wird, die es benötigt, um die angeforderte Anzahl oder Dauer zu füllen.  
  
 In der Standardeinstellung haben Zeitachsen eine Wiederholungsanzahl von 1.0, d. h., sie wird einmal abgespielt und nicht wiederholt. Allerdings setzen Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die Zeitachse unbegrenzt wiederholt.  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um das Wiederholungsverhalten einer Animation steuern. Das Beispiel erstellt eine Animation die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft fünf Rechtecke mit jedes Rechtecks mithilfe eines anderen Typs des Wiederholungsverhaltens.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Animation Timing Verhalten Sample](https://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>Siehe auch

- [Sammeln von Animationen während Wiederholungszyklen](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Festlegen, ob eine Zeitachse automatisch umgekehrt wird](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen](animation-and-timing-how-to-topics.md)
- [Übersicht über Animationen](animation-overview.md)
- [Beispiel zum Verhalten der Animationszeitsteuerung](https://go.microsoft.com/fwlink/?LinkID=159970)
