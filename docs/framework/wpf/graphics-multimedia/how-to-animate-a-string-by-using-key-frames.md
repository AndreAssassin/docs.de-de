---
title: 'Vorgehensweise: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4a37408ad90fda12a95e66c1b44018967b376837
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204171"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Vorgehensweise: Animieren einer Zeichenfolge mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie eine Zeichenfolge, animieren, die in diesem Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button> -Steuerelement, mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.  
  
 Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> Klasse, da die Animation einer Zeichenfolge, die mit Keyframes erstellt wird nur diskrete Keyframes verwenden kann. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, Änderungen an der Animation schnell erfolgen und nicht subtil.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
