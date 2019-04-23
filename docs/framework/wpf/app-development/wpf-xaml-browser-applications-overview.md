---
title: Übersicht über WPF-XAML-Browseranwendungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
ms.openlocfilehash: 81ae93871fa5e3fc46382ee9a1810808574fb043
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320131"
---
# <a name="wpf-xaml-browser-applications-overview"></a>Übersicht über WPF-XAML-Browseranwendungen
<a name="introduction"></a>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] kombiniert die Funktionen von Webanwendungen und Rich Client-Anwendungen. Wie Webanwendungen können XBAPs auf einem Webserver bereitgestellt werden und aus Internet Explorer oder Firefox gestartet werden. Wie Rich Client-Anwendungen können XBAPs Funktionen von WPF nutzen. Auch die Entwicklung von XBAPs ähnelt der Rich Client-Entwicklung. Dieses Thema bietet eine allgemeine einfache Einführung in die XBAP-Entwicklung und beschreibt die Unterschiede zwischen der Entwicklung von XBAP und standardmäßigen Rich Client-Anwendungen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Erstellen einer neuen XAML-Browseranwendung (XBAP)](#creating_a_new_xaml_browser_application_xbap)  
  
-   [Bereitstellen einer XBAP](#deploying_a_xbap)  
  
-   [Kommunizieren mit der Hostwebseite](#communicating_with_the_host_web_page)  
  
-   [XBAP-Sicherheitsüberlegungen](#xbap_security_considerations)  
  
-   [Überlegungen zur XBAP-Startzeitleistung](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## <a name="creating-a-new-xaml-browser-application-xbap"></a>Erstellen einer neuen XAML-Browseranwendung (XBAP)  
 Die einfachste Möglichkeit zum Erstellen eines neuen XBAP-Projekts ist mit Microsoft Visual Studio. Wenn Sie ein neues Projekt erstellen, wählen Sie **WPF-Browseranwendung** aus der Liste der Vorlagen aus. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen ein neues WPF-Browseranwendungsprojekts](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).  
  
 Wenn Sie das XBAP-Projekt ausführen, wird es in einem Browserfenster geöffnet, nicht in einem eigenständigen Fenster. Wenn Sie die XBAP aus Visual Studio debuggen, wird die Anwendung mit Internetzonenberechtigung ausgeführt und löst daher Sicherheitsausnahmen aus, wenn diese Berechtigungen überschritten werden. Weitere Informationen finden Sie unter[ Sicherheit (WPF)](../security-wpf.md) und [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
> [!NOTE]
>  Wenn Sie nicht mit Visual Studio oder möchten Sie weitere Informationen zu den Projektdateien entwickeln, finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
<a name="deploying_a_xbap"></a>   
## <a name="deploying-an-xbap"></a>Bereitstellen einer XBAP  
 Wenn Sie eine XBAP erstellen, schließt die Ausgabe die folgenden drei Dateien ein:  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|Ausführbare Datei (.exe)|Diese enthält den kompilierten Code und hat die Erweiterung EXE.|  
|Anwendungsmanifest (.manifest)|Dieses enthält die der Anwendung zugeordneten Metadaten und hat die Erweiterung MANIFEST.|  
|Bereitstellungsmanifest (.xbap)|Diese Datei enthält die Information, dass ClickOnce zum Bereitstellen der Anwendung verwendet und die Erweiterung XBAP hat.|  
  
 Sie stellen XBAPs auf einem Webserver, z.B. [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] oder höheren Versionen, bereit. Sie müssen keine .NET Framework auf dem Webserver zu installieren, aber Sie müssen zum Registrieren der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] Typen und-Dateierweiterungen. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen](how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).  
  
 Zum Vorbereiten der XBAP für die Bereitstellung kopieren Sie die EXE-Datei und die zugeordneten Manifeste auf den Webserver. Erstellen Sie eine HTML-Seite, die einen Link enthält, um das Bereitstellungsmanifest zu öffnen. Dabei handelt es sich um die Datei mit der Erweiterung XBAP. Wenn der Benutzer auf den Link zur XBAP-Datei klickt, erledigt ClickOnce automatisch herunterladen und Starten der Anwendung. Im folgenden Beispielcode wird eine HTML-Seite dargestellt, die einen Link enthält, der auf eine XBAP zeigt.  
  
```html
<html>   
    <head></head>  
    <body>   
        <a href="XbapEx.xbap">Click this link to launch the application</a>  
    </body>   
</html>  
```  
  
 Sie können eine XBAP auch im Frame einer Webseite hosten. Erstellen Sie eine Webseite mit einem oder mehreren Frames. Legen Sie die Quelleigenschaft eines Frames auf die Bereitstellungsmanifestdatei fest. Wenn Sie den integrierten Mechanismus verwenden möchten, um zwischen der Hostingwebseite und der XBAP zu kommunizieren, müssen Sie die Anwendung in einem Frame hosten. Im folgenden Beispielcode ist eine HTML-Seite mit zwei Frames dargestellt, wobei die Quelle für den zweiten Frame auf eine XBAP festgelegt ist.  
  
```html
<html>   
    <head>
        <title>A page with frames</title>
    </head>  
    <frameset cols="50%,50%">   
        <frame src="introduction.htm">   
        <frame src="XbapEx.xbap">   
    </frameset>   
</html>  
```  
  
### <a name="clearing-cached-xbaps"></a>Löschen von zwischengespeicherten XBAPs  
 In einigen Situationen stellen Sie nach dem Neuerstellen und Starten der XBAP fest, dass eine frühere Version der XBAP geöffnet wird. Dieses Verhalten kann beispielsweise auftreten, wenn die XBAP-Assemblyversionsnummer statisch ist und Sie die XBAP über die Befehlszeile starten. In diesem Fall ist, da die Versionsnummer zwischen der zwischengespeicherten Version (die Version, die zuvor gestartet wurde) und die neue Version unverändert, die neue Version der XBAP nicht heruntergeladen. Stattdessen wird die zwischengespeicherte Version geladen.  
  
 In diesen Fällen können Sie die zwischengespeicherte Version entfernen, indem Sie mit der **Mage** Befehl (mit Visual Studio oder das Windows SDK installiert), an der Eingabeaufforderung. Der folgende Befehl löscht den Anwendungscache.  
  
 ```console
 Mage.exe -cc
 ```
  
 Dieser Befehl gewährleistet, dass die neueste Version der XBAP gestartet wird. Wenn Sie Ihre Anwendung in Visual Studio debuggen, sollten die neueste Version der XBAP gestartet werden. Es wird empfohlen, die Bereitstellungsversionsnummer mit jedem Build zu aktualisieren. Weitere Informationen über Mage finden Sie unter [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
<a name="communicating_with_the_host_web_page"></a>   
## <a name="communicating-with-the-host-web-page"></a>Kommunizieren mit der Hostwebseite  
 Wenn die Anwendung in einem HTML-Frame gehostet wird, können Sie mit der Webseite kommunizieren, die die XBAP enthält. Sie dazu die <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> Eigenschaft <xref:System.Windows.Interop.BrowserInteropHelper>. Diese Eigenschaft gibt ein Skriptobjekt zurück, das das HTML-Fenster darstellt. Sie können dann auf die Eigenschaften, Methoden und Ereignisse auf dem [Fensterobjekt](https://go.microsoft.com/fwlink/?LinkId=160274) mit regulärer Punktsyntax zugreifen. Sie können auch auf Skriptmethoden und globale Variablen zugreifen. Im folgenden Beispiel wird veranschaulicht, wie Sie das Skriptobjekt abrufen und den Browser schließen.  
  
 [!code-csharp[XbapBrowserInterop#10](~/samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### <a name="debugging-xbaps-that-use-hostscript"></a>Debuggen von XBAPs, die HostScript verwenden  
 Wenn die XBAP verwendet die <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> Objekt für die Kommunikation mit dem HTML-Fenster, es gibt zwei Einstellungen, die Sie angeben müssen, um die Anwendung in Visual Studio ausführen und Debuggen. Die Anwendung muss Zugriff auf ihre Ursprungssite haben, und Sie müssen die Anwendung mit der HTML-Seite starten, die die XBAP enthält. Die folgenden Schritte beschreiben, wie diese beiden Einstellungen überprüft werden:  
  
1. Öffnen Sie die Projekteigenschaften in Visual Studio.  
  
2. Klicken Sie auf der Registerkarte **Sicherheit** auf **Erweitert**.  
  
     Das Dialogfeld „Erweiterte Sicherheitseinstellungen“wird angezeigt.  
  
3. Stellen Sie sicher, dass das Kontrollkästchen **Der Anwendung Zugriff auf die Ursprungssite gewähren** aktiviert ist, und klicken Sie dann auf **OK**.  
  
4. Wählen Sie auf der Registerkarte **Debuggen** die Option **Browser mit folgender URL starten** aus, und geben Sie die URL für die HTML-Seite an, die die XBAP enthält.  
  
5. Klicken Sie in Internet Explorer auf die Schaltfläche **Extras**, und wählen Sie dann **Internetoptionen** aus.  
  
     Das Dialogfeld "Internetoptionen" wird angezeigt.  
  
6. Klicken Sie auf die Registerkarte **Erweitert**.  
  
7. Aktivieren Sie in der Liste **Einstellungen** unter **Sicherheit** das Kontrollkästchen **Ausführung aktiver Inhalte in Dateien auf dem lokalen Computer zulassen**.  
  
8. Klicken Sie auf **OK**.  
  
     Die Änderungen werden wirksam, nachdem Sie Internet Explorer neu gestartet haben.  
  
> [!CAUTION]
>  Aktiven Inhalt in Internet Explorer zu aktivieren, gefährdet möglicherweise den Computer. Wenn Sie nicht, um die Internet Explorer-Sicherheitseinstellungen zu ändern möchten, Sie starten die HTML-Seite von einem Server und Visual Studio-Debugger an den Prozess angehängt.  
  
<a name="xbap_security_considerations"></a>   
## <a name="xbap-security-considerations"></a>XBAP-Sicherheitsüberlegungen  
 XBAPs werden in der Regel in einem teilweise vertrauenswürdigen Sicherheitsbereich (Sandbox) ausgeführt, der auf den Berechtigungssatz für die Internetzone beschränkt ist. Daher muss Ihre Implementierung die Teilmenge von WPF-Elementen, die in der Internetzone unterstützt werden unterstützen, oder Sie müssen die Berechtigungen der Anwendung erhöhen. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../security-wpf.md).  
  
 Bei Verwendung einer <xref:System.Windows.Controls.WebBrowser> Steuerelement in der WPF-Anwendung instanziiert intern das native WebBrowser ActiveX-Steuerelement. Wenn die Anwendung eine teilweise vertrauenswürdige XBAP ist, die in Internet Explorer ausgeführt wird, wird das ActiveX-Steuerelement in einem dedizierten Thread des Internet Explorer-Prozesses ausgeführt. Daher gelten die folgenden Einschränkungen:  
  
-   Die <xref:System.Windows.Controls.WebBrowser> Steuerelement sollte an den Hostbrowser, einschließlich sicherheitseinschränkungen ein ähnliches Verhalten bereitstellen. Einige dieser Sicherheitseinschränkungen können durch die Internet Explorer-Sicherheitseinstellungen gesteuert werden. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../security-wpf.md).  
  
-   Eine Ausnahme wird ausgelöst, wenn eine XBAP domänenübergreifend in eine HTML-Seite geladen wird.  
  
-   Die Eingabe erfolgt in einem separaten Thread aus dem WPF- <xref:System.Windows.Controls.WebBrowser>, sodass Tastatureingaben nicht abgefangen werden können, und der IME-Zustand nicht freigegeben.  
  
-   Die zeitliche Steuerung oder die Reihenfolge der Navigation weicht möglicherweise ab, da das ActiveX-Steuerelement in einem anderen Thread ausgeführt wird. Zum Beispiel wird die Navigation zu einer Seite nicht immer abgebrochen, indem eine andere Navigationsanforderung gestartet wird.  
  
-   Ein benutzerdefiniertes ActiveX-Steuerelement hat möglicherweise Probleme mit Kommunikation, da die WPF-Anwendung in einem separaten Thread ausgeführt wird.  
  
-   <xref:System.Windows.Interop.HwndHost.MessageHook> wird nicht ausgelöst, da <xref:System.Windows.Interop.HwndHost> kann nicht als Unterklasse eines Fensters in einem anderen Thread oder Prozess ausgeführt wird.  
  
### <a name="creating-a-full-trust-xbap"></a>Erstellen einer XBAP mit voller Vertrauenswürdigkeit  
 Wenn die XBAP volle Vertrauenswürdigkeit erfordert, können Sie das Projekt ändern, um diese Berechtigung zu aktivieren. Die folgenden Schritte beschreiben, wie volle Vertrauenswürdigkeit aktiviert wird:  
  
1. Öffnen Sie die Projekteigenschaften in Visual Studio.  
  
2. Aktivieren Sie die Option **Voll vertrauenswürdige Anwendung** auf der Registerkarte **Sicherheit**.  
  
 Diese Einstellung nimmt die folgenden Änderungen vor:  
  
-   In der Projektdatei wird der `<TargetZone>`-Elementwert in `Custom` geändert.  
  
-   Im Anwendungsmanifest (app.manifest) wird eine `Unrestricted="true"` -Attribut hinzugefügt, die "<xref:System.Security.PermissionSet> Element.  
  
    ```xml
    <PermissionSet class="System.Security.PermissionSet"   
                   version="1"   
                   ID="Custom"   
                   SameSite="site"   
                   Unrestricted="true" />  
    ```  
  
### <a name="deploying-a-full-trust-xbap"></a>Bereitstellen einer XBAP mit voller Vertrauenswürdigkeit  
 Wenn Sie eine vollständig vertrauenswürdige XBAP bereitstellen, die nicht dem ClickOnce Trusted-Bereitstellungsmodell folgt, hängt das Verhalten bei der Ausführung der Anwendung durch den Benutzer von der Sicherheitszone ab. In einigen Fällen erhält der Benutzer bei der Installation eine Warnung. Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll. In der folgenden Tabelle werden das Verhalten der Anwendung für jede Sicherheitszone und die erforderlichen Schritte für die volle Vertrauenswürdigkeit der Anwendung beschrieben.  
  
|Sicherheitszone|Verhalten|Erhalten der vollen Vertrauenswürdigkeit|  
|-------------------|--------------|------------------------|  
|Lokaler Computer|Automatisch volle Vertrauenswürdigkeit|Es ist keine Aktion erforderlich.|  
|Intranet und vertrauenswürdige Websites|Eingabeaufforderung für volle Vertrauenswürdigkeit|Signieren Sie die XBAP mit einem Zertifikat, damit der Benutzer die Quelle in der Eingabeaufforderung sieht.|  
|Internet|Schlägt fehl mit „Vertrauenswürdigkeit nicht gewährt“|Signieren Sie die XBAP mit einem Zertifikat.|  
  
> [!NOTE]
>  Das in der obigen Tabelle beschriebene Verhalten gilt für vollständig vertrauenswürdige XBAPs, die nicht dem ClickOnce Trusted-Bereitstellungsmodell folgen.  
  
 Es wird empfohlen, dass Sie das ClickOnce Trusted-Bereitstellungsmodell zum Bereitstellen einer vollständig vertrauenswürdigen XBAP verwenden. Mit diesem Modell können Sie der XBAP unabhängig von der Sicherheitszone automatisch die volle Vertrauenswürdigkeit gewähren lassen, sodass der Benutzer nicht aufgefordert wird. Als Teil dieses Modells müssen Sie die Anwendung mit einem Zertifikat für einen vertrauenswürdigen Verleger signieren. Weitere Informationen finden Sie unter [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview) und [Introduction to Code Signing (Einführung in die Codesignatur)](https://go.microsoft.com/fwlink/?LinkId=166327).  
  
<a name="xbap_start_time_performance_considerations"></a>   
## <a name="xbap-start-time-performance-considerations"></a>Überlegungen zur XBAP-Startzeitleistung  
 Ein wichtiger Aspekt der XBAP-Leistung ist ihre Startzeit. Falls eine XPAB die erste zu ladende WPF-Anwendung darstellt, kann die *Kaltstartzeit* zehn Sekunden oder mehr betragen. Dies ist darauf zurückzuführen, dass die Statusseite von WPF gerendert wird und sowohl die CLR als auch WPF für die Anzeige der Anwendung kaltgestartet werden müssen.  
  
 Wenn Sie in [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] starten, wird die XBAP-Kaltstartzeit reduziert, indem eine nicht verwaltete Statusseite in einer frühen Phase im Bereitstellungszyklus angezeigt wird. Die Statusseite wird fast unmittelbar nach dem Start der Anwendung angezeigt, da sie mit nativen Hostingcode angezeigt und in HTML gerendert wird.  
  
 Darüber hinaus wird die verbesserte Parallelität von der ClickOnce-Download-Sequenz Startzeit um bis zu zehn Prozent verbessert. Nachdem ClickOnce heruntergeladen und überprüft wird Manifeste, beginnt der Anwendungsdownload und die Statusanzeige aktualisiert.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen](configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)
- [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)
