---
title: 'Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: e96e1772794a1594d97e1a0109d944d23515468d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100885"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs
Dieses Beispiel zeigt, wie Sie programmgesteuert einen Adorner an die untergeordneten Elemente eines angegebenen binden <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Beispiel  
 Zum Binden eines Adorners an die untergeordneten Elemente ein <xref:System.Windows.Controls.Panel>, gehen Sie folgendermaßen vor:  
  
1.  Deklarieren Sie eine neue <xref:System.Windows.Documents.AdornerLayer> Objekt, und rufen die `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode, um eine Adornerebene für das Element gesucht, deren untergeordnete Elemente zu verzieren sind.  
  
2.  Blättern Sie durch die untergeordneten Elemente des übergeordneten Elements, und rufen die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um einen Adorner an jedes untergeordnete Element binden.  
  
 Im folgende Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente gebunden. eine <xref:System.Windows.Controls.StackPanel> mit dem Namen *MyStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Adorner](adorners-overview.md)
