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
# <a name="how-to-get-and-set-the-main-application-window"></a>Vorgehensweise: Abrufen und Festlegen des Hauptfensters der Anwendung
Dieses Beispiel veranschaulicht das Abrufen und Festlegen des Hauptfensters der Anwendung.  
  
## <a name="example"></a>Beispiel  
 Die erste <xref:System.Windows.Window> instanziiert, die in einer Windows Presentation Foundation (WPF) Anwendung automatisch, indem festgelegt wird <xref:System.Windows.Application> als Hauptfenster der Anwendung. Die erste <xref:System.Windows.Window> , instanziiert wird, die sehr wahrscheinlich das Fenster sein, die als Start-angegeben wird [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (finden Sie unter <xref:System.Windows.Application.StartupUri%2A>).  
  
 Die erste <xref:System.Windows.Window> kann auch mithilfe von Code instanziiert werden. Ein Beispiel ist ein Fenster beim Start der Anwendung wie folgt öffnen:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 In einigen Fällen das erste instanziiert <xref:System.Windows.Window> ist nicht tatsächlich das Hauptanwendungsfenster z. B. einen Begrüßungsbildschirm. In diesem Fall können Sie das Hauptanwendungsfenster, der mit Markup, ähnlich dem folgenden angeben:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Ob das Hauptfenster automatisch oder manuell angegeben wird, erhalten Sie im Hauptfenster von <xref:System.Windows.Application.MainWindow%2A> mit dem folgenden Code, wie folgt:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
