---
title: Anwendungsentwicklung
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 3b7e1d04173741088935104e8d4225691927a27b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951592"
---
# <a name="application-development"></a>Anwendungsentwicklung
<a name="introduction"></a> Windows Presentation Foundation (WPF) ist ein Präsentationsframework, das verwendet werden kann, um die folgenden Arten von Anwendungen zu entwickeln:  
  
- Eigenständige Anwendungen: Herkömmliche [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Anwendungen, die als ausführbare Assemblys erstellt, auf dem Clientcomputer installiert und von dort ausgeführt werden.  
  
- [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]: Aus Navigationsseiten bestehende Anwendungen, die als ausführbare Assemblys erstellt und von Webbrowsern wie [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] oder Mozilla Firefox gehostet werden.  
  
- Benutzerdefinierte Steuerelementbibliotheken: Nicht ausführbare Assemblys mit wiederverwendbaren Steuerelementen.  
  
- Klassenbibliotheken: Nicht ausführbare Assemblys mit wiederverwendbaren Klassen.  
  
> [!NOTE]
>  Es wird dringend davon abgeraten, WPF-Typen in einem Windows-Dienst zu verwenden. Diese Funktionen funktionieren in einem Windows-Dienst möglicherweise nicht wie erwartet.  
  
 Um diesen Anwendungssatz zu erstellen, implementiert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eine Reihe von Diensten. Dieses Thema bietet eine Übersicht über diese Dienste sowie Verweise auf weitere Informationen.  

<a name="Application_Management"></a>   
## <a name="application-management"></a>Anwendungsverwaltung  
 Ausführbare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen erfordern im Allgemeinen eine Reihe wesentlicher Funktionen, die unter anderem folgende Vorgänge ermöglichen:  
  
- Erstellen und Verwalten einer allgemeinen Anwendungsinfrastruktur (einschließlich der Erstellung einer Einstiegspunktmethode und einer Windows-Meldungsschleife zum Empfangen von System- und Eingabenachrichten)  
  
- Verfolgen und Beeinflussen der Lebensdauer einer Anwendung  
  
- Abrufen und Verarbeiten von Befehlszeilenparametern  
  
- Freigeben von Eigenschaften für den Anwendungsbereich und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Ressourcen  
  
- Erkennen und Verarbeiten von Ausnahmefehlern (unbehandelten Ausnahmen)  
  
- Zurückgeben von Exitcodes  
  
- Verwalten von Fenstern in eigenständigen Anwendungen  
  
- Verfolgen der Navigation in [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und eigenständigen Anwendungen mit Navigationsfenstern und Frames  
  
 Diese Funktionen werden von der <xref:System.Windows.Application>-Klasse implementiert, die Sie Ihren Anwendungen mit einer *Anwendungsdefinition* hinzufügen.  
  
 Weitere Informationen finden Sie unter [Übersicht über die Anwendungsverwaltung](application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a>WPF-Anwendungsressource, Inhalts- und Datendateien  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Erweitert die Core-Unterstützung in Microsoft .NET Framework für eingebettete Ressourcen mit Unterstützung für drei Arten von nicht ausführbaren Datendateien: Ressourcen, Inhalt und Daten. Weitere Informationen finden Sie unter [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md).  
  
 Ein wesentlicher Faktor der Unterstützung von nicht ausführbaren WPF-Datendateien ist die Möglichkeit, diese mit einem eindeutigen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] zu identifizieren und zu laden. Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a>Fenster und Dialogfelder  
 Benutzer interagieren über Fenster mit eigenständigen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen. Fenster dienen dazu, Anwendungsinhalte zu hosten und Anwendungsfunktionen, über die Benutzer mit diesen Inhalten interagieren können, verfügbar zu machen. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] werden Fenster von der <xref:System.Windows.Window>-Klasse gekapselt, die folgende Vorgänge unterstützt:  
  
- Erstellen und Anzeigen von Fenstern  
  
- Einrichten von Beziehungen „Besitzer/zum Besitzer gehöriges Fenster“  
  
- Konfigurieren der Fensterdarstellung (z. B. Größe, Position, Symbole, Titelleistentext und Rahmen)  
  
- Verfolgen und Beeinflussen der Lebensdauer eines Fensters  
  
 Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> unterstützt die Erstellung einer besonderen Art von Fenster, nämlich von Dialogfeldern. Es können sowohl modale als auch nicht modale Dialogfelder (Dialogfelder ohne Modus) erstellt werden.  
  
 Zur Vereinfachung und die Vorteile der wiederverwendbarkeit und Benutzern eine konsistente Umgebung für Anwendungen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] macht drei von der Windows-Standarddialogfelder: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, und <xref:System.Windows.Controls.PrintDialog>.  
  
 Ein Meldungsfeld ist eine besondere Art von Dialogfeld, in dem Benutzern wichtige Informationen angezeigt und einfache Ja/Nein/OK/Abbrechen-Fragen gestellt werden. Sie verwenden die <xref:System.Windows.MessageBox>-Klasse zum Erstellen und Anzeigen von Meldungsfeldern.  
  
 Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](dialog-boxes-overview.md).  
  
<a name="Navigation"></a>   
## <a name="navigation"></a>Navigation  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] unterstützt die Navigation im Webstil über Seiten (<xref:System.Windows.Controls.Page>) und Links (<xref:System.Windows.Documents.Hyperlink>). Die Navigation kann unter anderem auf folgende Weise implementiert werden:  
  
- Eigenständige Seiten, die in einem Webbrowser gehostet werden  
  
- In eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] kompilierte Seiten, die in einem Webbrowser gehostet werden  
  
- Als eigenständige Anwendung kompilierte Seiten, die von einem Navigationsfenster (<xref:System.Windows.Navigation.NavigationWindow>) gehostet werden  
  
- Von einem Frame gehostete Seiten (<xref:System.Windows.Controls.Frame>), die in einer eigenständigen Seite oder in einer als [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] oder eigenständige Anwendung kompilierten Seite gehostet werden können  
  
 Zur Unterstützung der Navigation implementiert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] folgende Elemente:  
  
- <xref:System.Windows.Navigation.NavigationService>, die freigegebene Navigations-Engine für die Verarbeitung von Navigationsanforderungen, das von <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow> und [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] zur Unterstützung der Navigation innerhalb von Anwendungen verwendet wird  
  
- Navigationsmethoden zur Einleitung der Navigation  
  
- Navigationsereignisse zum Verfolgen und Beeinflussen der Navigationslebensdauer  
  
- Aufzeichnung von Vorwärts- und Rückwärtsnavigation mithilfe eines „Journals“, das auch überprüft und bearbeitet werden kann  
  
 Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md).  
  
 Darüber hinaus unterstützt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die strukturierte Navigation. Die strukturierte Navigation kann zum Aufruf einer oder mehrerer Seiten verwendet werden, die Daten auf strukturierte und vorhersagbare Weise in Übereinstimmung mit den aufrufenden Funktionen zurückgeben. Diese Funktion ist abhängig von der <xref:System.Windows.Navigation.PageFunction%601>-Klasse, die unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md) genauer beschrieben wird. <xref:System.Windows.Navigation.PageFunction%601> vereinfacht zudem die Erstellung komplexer Navigationstopologien, die unter [Übersicht über Navigationstopologien](navigation-topologies-overview.md) vorgestellt werden.  
  
<a name="Hosting"></a>   
## <a name="hosting"></a>Hosting  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s können in [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] oder Firefox gehostet werden. Bei jedem Hostmodell sind spezifische Punkte und Einschränkungen zu beachten, die unter [Hosten](hosting-wpf-applications.md) erläutert werden.  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a>Erstellen und Bereitstellen  
 Einfache [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen können über eine Eingabeaufforderung mithilfe von Befehlszeilencompilern erstellt werden. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kann jedoch auch in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] integriert werden und bietet dann zusätzliche Funktionen, die den Entwicklungs- und Erstellungsprozess vereinfachen. Weitere Informationen finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
 Je nach Art der erstellten Anwendung können Sie eine oder mehrere Bereitstellungsoptionen wählen. Weitere Informationen finden Sie unter [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über die Anwendungsverwaltung](application-management-overview.md)|Hier finden Sie eine Übersicht über die <xref:System.Windows.Application>-Klasse. Erörtert wird u.a. die Verwaltung von Anwendungslebensdauer, Fenstern, Anwendungsressourcen und Navigation.|  
|[Fenster in WPF](windows-in-wpf-applications.md)|Hier finden Sie Informationen zur Verwaltung von Fenstern in der Anwendung. Erörtert wird u.a. die Verwendung der <xref:System.Windows.Window>-Klasse und von Dialogfeldern.|  
|[Übersicht über die Navigation](navigation-overview.md)|Hier finden Sie eine Übersicht über die Verwaltung der Navigation zwischen Seiten der Anwendung.|  
|[Hosting](hosting-wpf-applications.md)|Enthält allgemeine Informationen zu [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].|  
|[Erstellen und Bereitstellen](building-and-deploying-wpf-applications.md)|Hier wird beschrieben, wie Sie die WPF-Anwendung erstellen und bereitstellen.|  
|[Einführung in WPF in Visual Studio](../getting-started/introduction-to-wpf-in-vs.md)|Hier werden die wichtigsten Funktionen von WPF beschrieben.|  
|[Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie eine WPF-Anwendung mit Seitennavigation, Layout, Steuerelementen, Bildern, Stilen und Bindung erstellen.|
