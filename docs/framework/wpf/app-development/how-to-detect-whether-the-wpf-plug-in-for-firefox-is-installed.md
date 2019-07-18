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
ms.openlocfilehash: f84a0a2af43931b3ada1f674390ec5d841b79a1c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690430"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Vorgehensweise: Erkennen einer Installation des WPF-Plug-Ins für Firefox

Die Windows Presentation Foundation-Plug-Ins für Firefox (WPF) können [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Loose XAML-Dateien in den Mozilla Firefox-Browser ausgeführt. Dieses Thema enthält ein Skript in HTML und JavaScript, die Administratoren verwenden können, um festzustellen, ob die Installation des WPF-Plug-Ins für Firefox geschrieben.

> [!NOTE]
> Weitere Informationen zum Installieren, bereitstellen und Erkennen von .NET Framework finden Sie unter [Installieren von .NET Framework für Entwickler](../../install/guide-for-developers.md).

## <a name="example"></a>Beispiel

Wenn .NET Framework 3.5 installiert ist, wird der Clientcomputer mit einem WPF-Plug-Ins für Firefox konfiguriert. Das folgende Beispielskript für das WPF-Plug-Ins für Firefox überprüft und dann eine entsprechende Statusmeldung angezeigt.

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

Wenn die Überprüfung für das WPF-Plug-Ins für Firefox erfolgreich ist, wird die folgende Statusmeldung angezeigt:

`The WPF plug-in for Firefox is installed.`

Andernfalls wird die folgende Statusmeldung angezeigt:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>Siehe auch

- [Erkennen einer .NET Framework 3.0-Installation](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Erkennen einer .NET Framework 3.5-Installation](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md)
