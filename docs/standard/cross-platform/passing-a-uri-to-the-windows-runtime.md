---
title: Übergeben eines URI an die Windows-Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c489ec893ea335c8fafc904cf2a12162580ec266
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025441"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Übergeben eines URI an die Windows-Runtime
Windows Runtime-Methoden akzeptieren nur absolute URIs. Wenn Sie einen relativen URI an eine Windows-Runtime-Methode, übergeben einen <xref:System.ArgumentException> Ausnahme ausgelöst. Erläuterung: Bei Verwendung der Windows-Runtime in .NET Framework-Code, der <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse angezeigt wird, als <xref:System.Uri?displayProperty=nameWithType> in Intellisense. Die <xref:System.Uri?displayProperty=nameWithType> -Klasse ermöglicht relative URIs, aber die <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse jedoch nicht. Dies gilt auch für Methoden, die Sie in der Windows-Runtime-Komponenten verfügbar machen. Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>. Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.  
  
In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Erkennen und Verwenden eines absoluten URIs  
Verwenden der <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an der Windows-Runtime übergeben. Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Verwenden eines absoluten URI für eine Ressource im App-Paket  
Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.  
  
Das folgende Beispiel zeigt, wie Sie festlegen der <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.WebView> Steuerelement und die <xref:Windows.UI.Xaml.Controls.Image.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.Image> Steuerung auf Ressourcen, die in einem Ordner namens Seiten, die mit XAML und Code enthalten sind.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Weitere Informationen über diese Schemas finden Sie unter [URI-Schemas](/windows/uwp/app-resources/uri-schemes) im Windows Dev Center.  
  
## <a name="see-also"></a>Siehe auch

- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
