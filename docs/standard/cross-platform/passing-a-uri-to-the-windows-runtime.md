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
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921380"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="a7fda-102">Übergeben eines URI an die Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="a7fda-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="a7fda-103">Windows Runtime-Methoden akzeptieren nur absolute URIs.</span><span class="sxs-lookup"><span data-stu-id="a7fda-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="a7fda-104">Wenn Sie einen relativen URI an eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Methode übergeben, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a7fda-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="a7fda-105">Erläuterung: Bei Verwendung der [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework-Code, der <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse angezeigt wird, als <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span><span class="sxs-lookup"><span data-stu-id="a7fda-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="a7fda-106">Die <xref:System.Uri?displayProperty=nameWithType> -Klasse ermöglicht relative URIs, aber die <xref:Windows.Foundation.Uri?displayProperty=nameWithType> -Klasse jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a7fda-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="a7fda-107">Dies gilt auch für Methoden, die Sie in [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="a7fda-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="a7fda-108">Wenn eine Komponente eine Methode verfügbar macht, die einen URI enthält, enthält die Signatur im Code <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7fda-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a7fda-109">Für Benutzer Ihrer Komponente enthält die Signatur jedoch <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a7fda-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a7fda-110">Ein URI, der an die Komponente übergeben wird, muss ein absoluter URI sein.</span><span class="sxs-lookup"><span data-stu-id="a7fda-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="a7fda-111">In diesem Thema wird erläutert, wie Sie einen absoluten URI erkennen und einen solchen erstellen, wenn Sie auf eine Ressource im App-Paket verweisen.</span><span class="sxs-lookup"><span data-stu-id="a7fda-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="a7fda-112">Erkennen und Verwenden eines absoluten URIs</span><span class="sxs-lookup"><span data-stu-id="a7fda-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="a7fda-113">Verwenden Sie die <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>-Eigenschaft, um sicherzustellen, dass ein URI absolut ist, bevor er an [!INCLUDE[wrt](../../../includes/wrt-md.md)] übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7fda-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="a7fda-114">Das Verwenden dieser Eigenschaft ist effizienter als das Abfangen und Behandeln der <xref:System.ArgumentException>-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a7fda-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="a7fda-115">Verwenden eines absoluten URI für eine Ressource im App-Paket</span><span class="sxs-lookup"><span data-stu-id="a7fda-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="a7fda-116">Wenn Sie einen URI für eine Ressource angeben möchten, der im App-Paket enthalten sein soll, können Sie das `ms-appx`-Schema oder `ms-appx-web`-Schema verwenden, um einen absoluten URI zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7fda-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="a7fda-117">Das folgende Beispiel zeigt, wie Sie festlegen der <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.WebView> Steuerelement und die <xref:Windows.UI.Xaml.Controls.Image.Source%2A> -Eigenschaft für eine <xref:Windows.UI.Xaml.Controls.Image> Steuerung auf Ressourcen, die in einem Ordner namens Seiten, die mit XAML und Code enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a7fda-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="a7fda-118">Weitere Informationen über diese Schemas finden Sie unter [URI-Schemas](/windows/uwp/app-resources/uri-schemes) im Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="a7fda-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fda-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7fda-119">See also</span></span>

- [<span data-ttu-id="a7fda-120">.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="a7fda-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
