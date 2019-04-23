---
title: 'Vorgehensweise: Verwenden der FontSizeConverter-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979354"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="4eaef-102">Vorgehensweise: Verwenden der FontSizeConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="4eaef-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="4eaef-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4eaef-103">Example</span></span>  
 <span data-ttu-id="4eaef-104">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Instanz von <xref:System.Windows.FontSizeConverter> und mit, dass Sie um eine Schriftgröße zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4eaef-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="4eaef-105">Das Beispiel definiert eine benutzerdefinierte Methode namens `changeSize` , der den Inhalt des konvertiert eine <xref:System.Windows.Controls.ListBoxItem>, wie definiert in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, um eine Instanz von <xref:System.Double>, und später in eine <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4eaef-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="4eaef-106">Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.FontSizeConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von einer <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="4eaef-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="4eaef-107">Dieser Wert übergeben wird dann wieder als Wert für die <xref:System.Windows.Controls.TextBlock.FontSize%2A> Eigenschaft der <xref:System.Windows.Controls.TextBlock> Element.</span><span class="sxs-lookup"><span data-stu-id="4eaef-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="4eaef-108">Dieses Beispiel definiert auch eine zweite benutzerdefinierte Methode, die aufgerufen wird `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="4eaef-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="4eaef-109">Diese Methode konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.String>, und übergibt dann diesen Wert auf die <xref:System.Windows.Controls.TextBlock.FontFamily%2A> Eigenschaft der <xref:System.Windows.Controls.TextBlock> Element.</span><span class="sxs-lookup"><span data-stu-id="4eaef-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="4eaef-110">Dieses Beispiel wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4eaef-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4eaef-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4eaef-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
