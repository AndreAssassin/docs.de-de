---
title: 'Vorgehensweise: Animieren eines Doubles mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 73cbeab8aee566313bad8e8a18a5500374287de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305584"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Vorgehensweise: Animieren eines Doubles mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie den Wert einer Eigenschaft zu animieren, akzeptiert eine <xref:System.Double> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Rechteck über den Bildschirm bewegt. Im Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft eine <xref:System.Windows.Media.TranslateTransform> angewendet werden, um eine <xref:System.Windows.Shapes.Rectangle>. In dieser sich ständig wiederholenden Animation werden drei Keyframes folgendermaßen verwendet:  
  
1. In den ersten drei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> Klasse, um das Rechteck entlang eines Pfads mit konstanter Geschwindigkeit von der Startposition bis zur Position 500 zu verschieben. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> einen glatten, linearen Übergang zwischen Werten zu erstellen.  
  
2. Am Ende der vierten Sekunde wird eine Instanz der dem <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> Klasse, um das Rechteck sofort an die nächste Position zu bewegen. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> ermöglichen abrupte Sprünge zwischen Werten. In diesem Beispiel befindet sich das Rechteck an der Startposition und wird anschließend plötzlich an der Position 500 angezeigt.  
  
3. In den letzten zwei Sekunden wird eine Instanz der dem <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> Klasse, um das Rechteck zurück an seine Ausgangsposition zu verschieben. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> erzeugen einen variablen Übergang zwischen Werten gemäß dem Wert des der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> Eigenschaft. In diesem Beispiel bewegt sich das Rechteck zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Verwenden Sie für Konsistenz mit anderen Animationsbeispielen die Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt anzuwendende der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Alternativ beim Anwenden einer Animation im Code ist es einfacher, den <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
