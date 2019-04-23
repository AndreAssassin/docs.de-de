---
title: 'Vorgehensweise: Verwenden eines ThicknessConverter-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: ebfb8642a01f6d602f4e5ffa58fde6a8ee0b4e1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075950"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="f17e3-102">Vorgehensweise: Verwenden eines ThicknessConverter-Objekts</span><span class="sxs-lookup"><span data-stu-id="f17e3-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="f17e3-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f17e3-103">Example</span></span>  
 <span data-ttu-id="f17e3-104">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Instanz von <xref:System.Windows.ThicknessConverter> und um die Breite eines Rahmens zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f17e3-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="f17e3-105">Das Beispiel definiert eine benutzerdefinierte Methode namens `changeThickness`; diese Methode zuerst konvertiert den Inhalt der ein <xref:System.Windows.Controls.ListBoxItem>, wie definiert in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, um eine Instanz von <xref:System.Windows.Thickness>, und konvertiert Sie den Inhalt in einem späteren Zeitpunkt eine <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f17e3-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="f17e3-106">Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.ThicknessConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von einer <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="f17e3-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="f17e3-107">Dieser Wert übergeben wird dann wieder als Wert für die <xref:System.Windows.Controls.Border.BorderThickness%2A> Eigenschaft der <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="f17e3-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="f17e3-108">Dieses Beispiel wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f17e3-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f17e3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f17e3-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="f17e3-110">[Vorgehensweise: Ändern Sie die Margin-Eigenschaft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f17e3-110">[How to: Change the Margin Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="f17e3-111">[Vorgehensweise: Konvertieren Sie ein ListBoxItem in einen neuen Typ von Daten](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f17e3-111">[How to: Convert a ListBoxItem to a new Data Type](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="f17e3-112">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="f17e3-112">Panels Overview</span></span>](../controls/panels-overview.md)
