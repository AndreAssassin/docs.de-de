---
title: 'Vorgehensweise: Erstellen eines StackPanel-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121809"
---
# <a name="how-to-create-a-stackpanel"></a>Vorgehensweise: Erstellen eines StackPanel-Objekts
Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.StackPanel> können Sie Elemente in einer bestimmten Richtung stapeln. Mithilfe von Eigenschaften, die auf definierten <xref:System.Windows.Controls.StackPanel>, Inhalt kann vertikal, dies ist die Standardeinstellung, oder horizontal.  
  
 Das folgende Beispiel Stapelt vertikal fünf <xref:System.Windows.Controls.TextBlock> Steuerelemente, die jeweils über einen anderen <xref:System.Windows.Controls.Border> und <xref:System.Windows.Controls.Border.Background%2A>, mithilfe von <xref:System.Windows.Controls.StackPanel>. Die untergeordneten Elemente, die keine angegebene <xref:System.Windows.FrameworkElement.Width%2A> gestreckt, um das übergeordnete Fenster auszufüllen, jedoch die untergeordneten Elemente umfassen, die einem angegebenen <xref:System.Windows.FrameworkElement.Width%2A>, im Fenster mittig platziert werden.  
  
 Die standardstapelrichtung in einem <xref:System.Windows.Controls.StackPanel> ist vertikal. Inhalt ablaufsteuerung in einem <xref:System.Windows.Controls.StackPanel>, verwenden die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft. Sie können die horizontale Ausrichtung steuern, mit der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.StackPanel>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Gewusst wie-Themen](stackpanel-how-to-topics.md)
