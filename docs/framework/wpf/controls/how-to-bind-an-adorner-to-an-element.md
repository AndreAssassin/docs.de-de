---
title: 'Vorgehensweise: Binden eines Adorners an ein Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: b6909fec466c2b31a7f4156c43b21a0c724f0217
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307287"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>Vorgehensweise: Binden eines Adorners an ein Element
Dieses Beispiel zeigt, wie Sie programmgesteuert einen Adorner an einem angegebenen binden <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Beispiel  
 Zum Binden eines Adorners an ein bestimmtes <xref:System.Windows.UIElement>, gehen Sie folgendermaßen vor:  
  
1. Aufrufen der `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> zum Abrufen einer <xref:System.Windows.Documents.AdornerLayer> -Objekt für die <xref:System.Windows.UIElement> verziert werden sollen. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> durchläuft die visuelle Struktur, beginnend am angegebenen **"UIElement"**, und gibt die erste Adornerebene gefundenen zurück. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)  
  
2. Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um den Adorner an das Ziel binden **"UIElement"**.  
  
 Im folgende Beispiel wird ein SimpleCircleAdorner, die (siehe oben), um eine <xref:System.Windows.Controls.TextBox> mit dem Namen *MyTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Adorner](adorners-overview.md)
