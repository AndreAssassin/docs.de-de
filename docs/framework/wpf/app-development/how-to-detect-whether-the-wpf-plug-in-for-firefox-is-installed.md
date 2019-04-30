---
title: 'Vorgehensweise: Erkennen einer Installation des WPF-Plug-Ins für Firefox'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 138c212e79654b8ac875628692b49bb6a38cb695
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947874"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="fc694-102">Vorgehensweise: Erkennen einer Installation des WPF-Plug-Ins für Firefox</span><span class="sxs-lookup"><span data-stu-id="fc694-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="fc694-103">Die Windows Presentation Foundation-Plug-Ins für Firefox (WPF) können [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Loose XAML-Dateien in den Mozilla Firefox-Browser ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc694-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="fc694-104">Dieses Thema enthält ein Skript in HTML und JavaScript, die Administratoren verwenden können, um festzustellen, ob die Installation des WPF-Plug-Ins für Firefox geschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc694-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="fc694-105">Weitere Informationen zu Installation, Bereitstellung und erkennen die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], finden Sie unter [Installieren von .NET Framework für Entwickler](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="fc694-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="fc694-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc694-106">Example</span></span>

<span data-ttu-id="fc694-107">Wenn die [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] ist installiert, der Clientcomputer mit einem WPF-Plug-Ins für Firefox konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fc694-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="fc694-108">Das folgende Beispielskript für das WPF-Plug-Ins für Firefox überprüft und dann eine entsprechende Statusmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc694-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

<span data-ttu-id="fc694-109">Wenn die Überprüfung für das WPF-Plug-Ins für Firefox erfolgreich ist, wird die folgende Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc694-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="fc694-110">Andernfalls wird die folgende Statusmeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fc694-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="fc694-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc694-111">See also</span></span>

- [<span data-ttu-id="fc694-112">Erkennen einer .NET Framework 3.0-Installation</span><span class="sxs-lookup"><span data-stu-id="fc694-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="fc694-113">Erkennen einer .NET Framework 3.5-Installation</span><span class="sxs-lookup"><span data-stu-id="fc694-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="fc694-114">Übersicht über WPF-XAML-Browseranwendungen</span><span class="sxs-lookup"><span data-stu-id="fc694-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
