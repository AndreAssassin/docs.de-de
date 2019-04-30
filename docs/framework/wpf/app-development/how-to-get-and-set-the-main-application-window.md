---
title: 'Vorgehensweise: Abrufen und Festlegen des Hauptfensters der Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: ea8333aa82f1159afb438215940ee1e7c2605e96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947796"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="f9cc3-102">Vorgehensweise: Abrufen und Festlegen des Hauptfensters der Anwendung</span><span class="sxs-lookup"><span data-stu-id="f9cc3-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="f9cc3-103">Dieses Beispiel veranschaulicht das Abrufen und Festlegen des Hauptfensters der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f9cc3-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9cc3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9cc3-104">Example</span></span>  
 <span data-ttu-id="f9cc3-105">Die erste <xref:System.Windows.Window> instanziiert, die in einer Windows Presentation Foundation (WPF) Anwendung automatisch, indem festgelegt wird <xref:System.Windows.Application> als Hauptfenster der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f9cc3-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="f9cc3-106">Die erste <xref:System.Windows.Window> , instanziiert wird, die sehr wahrscheinlich das Fenster sein, die als Start-angegeben wird [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (finden Sie unter <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="f9cc3-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="f9cc3-107">Die erste <xref:System.Windows.Window> kann auch mithilfe von Code instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9cc3-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="f9cc3-108">Ein Beispiel ist ein Fenster beim Start der Anwendung wie folgt öffnen:</span><span class="sxs-lookup"><span data-stu-id="f9cc3-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="f9cc3-109">In einigen Fällen das erste instanziiert <xref:System.Windows.Window> ist nicht tatsächlich das Hauptanwendungsfenster z. B. einen Begrüßungsbildschirm.</span><span class="sxs-lookup"><span data-stu-id="f9cc3-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="f9cc3-110">In diesem Fall können Sie das Hauptanwendungsfenster, der mit Markup, ähnlich dem folgenden angeben:</span><span class="sxs-lookup"><span data-stu-id="f9cc3-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="f9cc3-111">Ob das Hauptfenster automatisch oder manuell angegeben wird, erhalten Sie im Hauptfenster von <xref:System.Windows.Application.MainWindow%2A> mit dem folgenden Code, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f9cc3-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
