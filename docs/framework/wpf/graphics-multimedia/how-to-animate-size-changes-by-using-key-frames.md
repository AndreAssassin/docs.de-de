---
title: 'Vorgehensweise: Animieren von Größenänderungen mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0629b6600444bd172af451fd7e970bff894d8047
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342361"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Vorgehensweise: Animieren von Größenänderungen mithilfe von Keyframes
In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.ArcSegment.Size%2A> Eigenschaft eine <xref:System.Windows.Media.ArcSegment>. In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. In der ersten halben Sekunde der Animation ist, wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> Klasse, um die Größe des Bogens graduell zu erhöhen. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.  
  
2. Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> Klasse, um die Größe des Bogens abrupt zu erhöhen. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, die die größenveränderung der treten plötzlich und sind nicht feine.  
  
3. Über die letzten zwei Sekunden wird eine Instanz der dem <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> Klasse, um die Größe des Bogens zu erhöhen. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
