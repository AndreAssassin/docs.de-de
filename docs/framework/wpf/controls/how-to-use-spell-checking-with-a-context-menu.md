---
title: 'Vorgehensweise: Verwenden der Rechtschreibprüfung mit einem Kontextmenü'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 72b24c386eb99140c9c2729688994b81f92e1a6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699148"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="d3626-102">Vorgehensweise: Verwenden der Rechtschreibprüfung mit einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="d3626-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="d3626-103">Standardmäßig werden beim Aktivieren der Rechtschreibprüfung in einem Bearbeitungssteuerelement wie <xref:System.Windows.Controls.TextBox> oder <xref:System.Windows.Controls.RichTextBox>, erhalten Sie die Optionen im Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="d3626-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="d3626-104">Beispielsweise Benutzern ein falsch geschriebenes Wort mit der rechten Maustaste, erhalten sie einen Satz von Rechtschreibvorschläge oder die Option zum **alle ignorieren**.</span><span class="sxs-lookup"><span data-stu-id="d3626-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="d3626-105">Wenn Sie das Standard-Kontextmenü mit Ihr eigenes benutzerdefiniertes Kontextmenü überschreiben, jedoch dieser Funktionalität verloren gegangen ist, und Sie Code schreiben, um die Rechtschreibprüfung-Funktion im Kontextmenü erneut aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d3626-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="d3626-106">Das folgende Beispiel zeigt, wie Sie dies aktivieren, auf eine <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d3626-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3626-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3626-107">Example</span></span>  
 <span data-ttu-id="d3626-108">Das folgende Beispiel zeigt die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] erstellt eine <xref:System.Windows.Controls.TextBox> mit einigen Ereignissen, die verwendet werden, um das Kontextmenü zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d3626-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="d3626-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3626-109">Example</span></span>  
 <span data-ttu-id="d3626-110">Das folgende Beispiel zeigt den Code, der das Kontextmenü implementiert.</span><span class="sxs-lookup"><span data-stu-id="d3626-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="d3626-111">Der Code verwendet hierfür mit einem <xref:System.Windows.Controls.RichTextBox> ist ähnlich.</span><span class="sxs-lookup"><span data-stu-id="d3626-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="d3626-112">Der Hauptunterschied besteht in der an übergebene Parameter die `GetSpellingError` Methode.</span><span class="sxs-lookup"><span data-stu-id="d3626-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="d3626-113">Für eine <xref:System.Windows.Controls.TextBox>, übergeben Sie den ganzzahlige Index der Position der Einfügemarke:</span><span class="sxs-lookup"><span data-stu-id="d3626-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="d3626-114">Für eine <xref:System.Windows.Controls.RichTextBox>, übergeben die <xref:System.Windows.Documents.TextPointer> , der die Position der Einfügemarke angibt:</span><span class="sxs-lookup"><span data-stu-id="d3626-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="d3626-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3626-115">See also</span></span>

- [<span data-ttu-id="d3626-116">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="d3626-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d3626-117">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d3626-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="d3626-118">Aktivieren der Rechtschreibprüfung in einem Textbearbeitungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="d3626-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="d3626-119">Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"</span><span class="sxs-lookup"><span data-stu-id="d3626-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
