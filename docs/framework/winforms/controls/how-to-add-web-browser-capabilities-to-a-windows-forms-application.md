---
title: 'Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: 29422ad384240b017b279795d07e3c8100fae493
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208799"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="19e26-102">Vorgehensweise: Hinzufügen von Webbrowserfunktionen zu einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="19e26-102">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>
<span data-ttu-id="19e26-103">Mit dem <xref:System.Windows.Forms.WebBrowser>-Steuerelement können Sie Webbrowserfunktionalität in Ihre Anwendung einbinden.</span><span class="sxs-lookup"><span data-stu-id="19e26-103">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="19e26-104">Das Steuerelement verhält sich standardmäßig wie ein Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="19e26-104">The control works like a Web browser by default.</span></span> <span data-ttu-id="19e26-105">Nach dem Laden einer Anfangs-URL durch Festlegen der <xref:System.Windows.Forms.WebBrowser.Url%2A>-Eigenschaft können Sie auf Hyperlinks klicken oder mit den entsprechenden Tastenkombinationen vorwärts oder rückwärts durch den Navigationsverlauf navigieren.</span><span class="sxs-lookup"><span data-stu-id="19e26-105">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="19e26-106">Über das Kontextmenü, das durch Klicken mit der rechten Maustaste angezeigt wird, können standardmäßig zusätzliche Browserfunktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="19e26-106">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="19e26-107">Sie können auch neue Dokumente öffnen, indem Sie sie auf dem Steuerelement ablegen.</span><span class="sxs-lookup"><span data-stu-id="19e26-107">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="19e26-108">Das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verfügt über verschiedene Eigenschaften, Methoden und Ereignisse, mit denen Sie ähnliche Benutzeroberflächenfeatures wie in Internet Explorer implementieren können.</span><span class="sxs-lookup"><span data-stu-id="19e26-108">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>  
  
 <span data-ttu-id="19e26-109">Im folgenden Beispielcode werden eine Adressleiste, typische Browserschaltflächen, ein Menü **Datei**, eine Statusleiste und eine Titelleiste mit dem Titel der aktuellen Seite implementiert.</span><span class="sxs-lookup"><span data-stu-id="19e26-109">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19e26-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19e26-110">Example</span></span>  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19e26-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="19e26-111">Compiling the Code</span></span>  
 <span data-ttu-id="19e26-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="19e26-112">This example requires:</span></span>  
  
-   <span data-ttu-id="19e26-113">Verweise auf die Assemblys `System`, `System.Drawing` und `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="19e26-113">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>  
  
 <span data-ttu-id="19e26-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="19e26-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="19e26-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="19e26-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e26-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19e26-116">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="19e26-117">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="19e26-117">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
