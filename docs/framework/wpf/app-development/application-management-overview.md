---
title: Übersicht über die Anwendungsverwaltung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: 687037d4299c8a53a2dcd644fd778081b5e7a0a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757349"
---
# <a name="application-management-overview"></a>Übersicht über die Anwendungsverwaltung
Alle Anwendungen nutzen in der Regel einen gemeinsamen Satz von Funktionen, der für die Implementierung und Verwaltung der Anwendung gilt. Dieses Thema enthält eine Übersicht über die Funktionen in der <xref:System.Windows.Application> Klasse zum Erstellen und Verwalten von Anwendungen.  

## <a name="the-application-class"></a>Die Application-Klasse  
 In WPF im Gültigkeitsbereich der Anwendung die Grundfunktionen gekapselt ist, der <xref:System.Windows.Application> Klasse. Die <xref:System.Windows.Application> Klasse enthält die folgenden Funktionen:  
  
- Lebensdauer der Anwendung nachverfolgen und mit ihr interagieren  
  
- Befehlszeilenparameter abrufen und verarbeiten  
  
- Nicht behandelte Ausnahmen erkennen und darauf reagieren  
  
- Anwendungsspezifische Eigenschaften und Ressourcen teilen  
  
- Fenster in eigenständigen Anwendungen verwalten  
  
- Navigation nachverfolgen und verwalten  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Ausführen allgemeiner Aufgaben mithilfe der Application-Klasse  
 Wenn Sie nicht alle Details der interessiert sind die <xref:System.Windows.Application> -Klasse, die folgende Tabelle enthält einige häufige Aufgaben für <xref:System.Windows.Application> und wie diese umgesetzt werden können. Weitere Informationen und entsprechenden Beispielcode finden Sie über die zugehörigen APIs und Themen.  
  
|Aufgabe|Ansatz|  
|----------|--------------|  
|Ein Objekt abrufen, das die aktuelle Anwendung darstellt.|Verwenden Sie die <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Einen Startbildschirm zu einer Anwendung hinzufügen.|Finden Sie unter [Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Eine Anwendung starten.|Verwenden Sie die <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>-Methode.|  
|Eine Anwendung beenden.|Verwenden der <xref:System.Windows.Application.Shutdown%2A> Methode der <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> Objekt.|  
|Argumente über die Befehlszeile abrufen.|Behandeln der <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignisses und verwenden Sie die <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> Eigenschaft. Ein Beispiel finden Sie unter den <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Ereignis.|  
|Exitcode der Anwendung abrufen und festlegen.|Legen Sie die <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> -Eigenschaft in der <xref:System.Windows.Application.Exit?displayProperty=nameWithType> Ereignishandler oder der Aufruf der <xref:System.Windows.Application.Shutdown%2A> -Methode und übergeben Sie eine ganze Zahl.|  
|Nicht behandelte Ausnahmen erkennen und darauf reagieren.|Behandeln der <xref:System.Windows.Application.DispatcherUnhandledException> Ereignis.|  
|Anwendungsspezifische Ressourcen abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Ein anwendungsspezifisches Ressourcenverzeichnis verwenden.|Finden Sie unter [ein anwendungsspezifisches Ressourcenverzeichnis verwenden](how-to-use-an-application-scope-resource-dictionary.md).|  
|Anwendungsspezifische Eigenschaften abrufen und festlegen.|Verwenden Sie die <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>-Eigenschaft.|  
|Den Zustand einer Anwendung abrufen und speichern.|Finden Sie unter [beibehalten und Wiederherstellen von Anwendungsbereichseigenschaften über Anwendungssitzungen](persist-and-restore-application-scope-properties.md).|  
|Datendateien ohne Code verwalten, einschließlich Ressourcendateien, Inhalts- und Ursprungssitedateien.|Finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](wpf-application-resource-content-and-data-files.md).|  
|Fenster in eigenständigen Anwendungen verwalten.|Weitere Informationen finden Sie unter [Übersicht über WPF-Fenster](wpf-windows-overview.md).|  
|Navigation überwachen und verwalten.|Finden Sie unter [Übersicht über die Navigation](navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Die Anwendungsdefinition  
 Nutzen Sie die Funktionalität der <xref:System.Windows.Application> -Klasse, müssen Sie eine Anwendungsdefinition implementieren. Eine Definition der WPF-Anwendung ist eine abgeleitete Klasse <xref:System.Windows.Application> und mit einer speziellen MSBuild-Einstellung konfiguriert ist.  

### <a name="implementing-an-application-definition"></a>Implementieren einer Anwendungsdefinition  
 Eine typische Definition für die WPF-Anwendung wird mithilfe von Markup und CodeBehind implementiert. Dadurch können Sie Anwendungseigenschaften und Ressourcen deklarativ mithilfe des Markups festlegen und Ereignisse registrieren, während mit CodeBehind Ereignisse behandelt und anwendungsspezifisches Verhalten implementiert wird.  
  
 Das folgende Beispiel veranschaulicht die Implementierung einer Anwendungsdefinition mithilfe von Markup und CodeBehind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Damit eine Markup- und eine CodeBehind-Datei zusammenarbeiten können, ist Folgendes erforderlich:  
  
- Im Markup der `Application` -Element muss enthalten der `x:Class` Attribut. Wenn die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup-Datei wird MSBuild zum Erstellen einer `partial` abgeleitete Klasse <xref:System.Windows.Application> und hat den Namen, die angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer XML-Namespacedeklaration für das XAML-Schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).
  
- Im Code-Behind muss die Klasse muss eine `partial` Klasse mit dem gleichen Namen, die angegeben wird die `x:Class` -Attribut im Markup und eine Ableitung muss <xref:System.Windows.Application>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wird (finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Wenn Sie ein neues WPF-Anwendungsprojekt oder WPF-Browseranwendungsprojekt mit Visual Studio erstellen, wird eine Anwendungsdefinition ist standardmäßig enthalten und wird mithilfe von Markup und CodeBehind definiert.  
  
 Dieser Code ist die Mindestanforderung zum Implementieren einer Anwendungsdefinition. Muss jedoch eine zusätzliche MSBuild-Konfiguration, die Definition für die Anwendung vor dem Erstellen und Ausführen der Anwendung vorgenommen werden.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Konfigurieren der Anwendungsdefinition für MSBuild  
 Eigenständige Anwendungen und XAML-Browseranwendungen (XBAPs) erfordern die Implementierung ein gewisses Maß an die Infrastruktur, bevor sie ausgeführt werden können. Der wichtigste Teil dieser Infrastruktur ist der Einstiegspunkt. Wenn eine Anwendung von einem Benutzer gestartet wird, ruft das Betriebssystem den Einstiegspunkt auf, der eine bekannte Funktion zum Starten von Anwendungen ist.  
  
 In der Vergangenheit mussten Entwickler je nach Technologie einen Teil oder sämtlichen Code selbst verfassen. Allerdings WPF generiert dieser Code für Sie, wenn die Markupdatei Ihrer Anwendungsdefinition, als ein MSBuild konfiguriert ist `ApplicationDefinition` -Element angegeben, wie in der folgenden MSBuild-Projektdatei dargestellt:  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Da die Code-Behind-Datei Code enthält, wird es als ein MSBuild gekennzeichnet `Compile` -Element angegeben, ist Sie normal.  
  
 Die Anwendung diese MSBuild-Konfigurationen auf die Markup- und Code-Behind-Dateien einer Anwendungsdefinition führt dazu, dass MSBuild zum Generieren von Code wie folgt:  
  
 [!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
 [!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]  
  
 Der resultierende Code ergänzt die Anwendungsdefinition um zusätzlichen Infrastrukturcode, einschließlich der Einstiegspunktmethode `Main`. Die <xref:System.STAThreadAttribute> Attribut gilt für die `Main` Methode, um anzugeben, dass der Hauptthread der Benutzeroberfläche für die WPF-Anwendung einen STA-Thread, der für WPF-Anwendungen erforderlich ist. Bei Aufruf `Main` erstellt eine neue Instanz der `App` vor dem Aufruf der `InitializeComponent` Methode zum Registrieren der Ereignisse, und legen Sie die Eigenschaften, die im Markup implementiert sind. Da `InitializeComponent` wird generiert, Sie müssen nicht explizit aufrufen `InitializeComponent` aus einer Anwendungsdefinition wie beim <xref:System.Windows.Controls.Page> und <xref:System.Windows.Window> Implementierungen. Zum Schluss die <xref:System.Windows.Application.Run%2A> aufgerufen, um die Anwendung zu starten.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Abrufen der aktuellen Anwendungsdomäne  
 Da die Funktionalität der <xref:System.Windows.Application> Klasse in einer Anwendung freigegeben werden, es können nur eine Instanz vorhanden sein. die <xref:System.Windows.Application> pro Klasse <xref:System.AppDomain>. Um dies zu erzwingen die <xref:System.Windows.Application> Klasse wird als Singleton-Klasse implementiert (finden Sie unter [Implementieren von Singleton in c#](https://go.microsoft.com/fwlink/?LinkId=100567)), das eine einzelne Instanz von sich selbst erstellt und der SAS mit dem `static` <xref:System.Windows.Application.Current%2A> Diese Eigenschaft.  
  
 Der folgende Code zeigt, wie Sie erhalten einen Verweis auf die <xref:System.Windows.Application> Objekt für die aktuelle <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> Gibt einen Verweis auf eine Instanz von der <xref:System.Windows.Application> Klasse. Einen Verweis auf Wunsch Ihre <xref:System.Windows.Application> abgeleitete Klasse Sie den Wert wandelt müssen der <xref:System.Windows.Application.Current%2A> -Eigenschaft, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Sie können den Wert der untersuchen <xref:System.Windows.Application.Current%2A> zu einem beliebigen Zeitpunkt während der Lebensdauer der ein <xref:System.Windows.Application> Objekt. Sie sollten dabei jedoch vorsichtig sein. Nach der <xref:System.Windows.Application> Klasse instanziiert wird, gibt es ein Zeitraum während der den Status der <xref:System.Windows.Application> -Objekts inkonsistent ist. Während dieses Zeitraums <xref:System.Windows.Application> ist die verschiedene Aufgaben Initialisierung, die von Ihrem Code erforderlich sind, ausgeführt wird, einschließlich der Einrichtung der Infrastruktur, Festlegen von Eigenschaften und Ereignisse registrieren. Wenn Sie versuchen, Sie verwenden die <xref:System.Windows.Application> Objekt während dieses Zeitraums wird der Code möglicherweise unerwartete Ergebnisse, insbesondere, wenn sie die verschiedenen abhängt <xref:System.Windows.Application> festzulegenden Eigenschaften.  
  
 Wenn <xref:System.Windows.Application> nach Abschluss der Initialisierung, seine Lebensdauer wirklich beginnt.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Anwendungslebensdauer  
 Die Lebensdauer einer WPF-Anwendung wird durch verschiedene Ereignisse, die vom ausgelöst werden gekennzeichnet <xref:System.Windows.Application> , damit Sie benachrichtigt, wenn die Anwendung gestartet wurde, wurde aktiviert und deaktiviert, und heruntergefahren wurde.  

<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Begrüßungsbildschirm  
 Ab der [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], Sie können angeben, ein Image aus, in einem Startfenster oder *Begrüßungsbildschirm*. Die <xref:System.Windows.SplashScreen> -Klasse macht es einfach, ein Startfenster anzuzeigen, während die Anwendung geladen wird. Die <xref:System.Windows.SplashScreen> Fenster erstellt und angezeigt werden, bevor Sie <xref:System.Windows.Application.Run%2A> aufgerufen wird. Weitere Informationen finden Sie unter [Anwendungsstartzeit](../advanced/application-startup-time.md) und [Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung](how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Starten einer Anwendung  
 Nach dem <xref:System.Windows.Application.Run%2A> aufgerufen wird und die Anwendung initialisiert wird, die Anwendung für die Ausführung bereit ist. Derzeit gekennzeichnet ist, wenn die <xref:System.Windows.Application.Startup> Ereignis wird ausgelöst:  
  
[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]
  
 An diesem Punkt ist der am häufigsten verwendete Schritt das in der Lebensdauer einer Anwendung, um eine Benutzeroberfläche anzuzeigen.  
  
<a name="Showing_a_User_Interface"></a>
### <a name="showing-a-user-interface"></a>Anzeigen einer Benutzeroberfläche  
 Öffnen Sie die meisten eigenständigen Windows-Anwendungen eine <xref:System.Windows.Window> wenn damit begonnen wird ausgeführt. Die <xref:System.Windows.Application.Startup> -Ereignishandler ist ein Speicherort, von dem Sie dies erreichen, wie im folgenden Code gezeigt.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Die erste <xref:System.Windows.Window> um zu instanziierenden in einer eigenständigen Anwendung standardmäßig die Befugnisse Hauptfensters der Anwendung. Dies <xref:System.Windows.Window> Objekt verweist auf die <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> Eigenschaft. Der Wert des der <xref:System.Windows.Application.MainWindow%2A> Eigenschaft kann programmgesteuert geändert werden, wenn ein anderes Fenster als das erste instanziiert <xref:System.Windows.Window> das Hauptfenster sein soll.  
  
 Beim ersten Start eine XBAP wird navigiert diese wahrscheinlich zu einer <xref:System.Windows.Controls.Page>. Dies wird im folgenden Code veranschaulicht.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Verarbeitet <xref:System.Windows.Application.Startup> nur öffnen eine <xref:System.Windows.Window> oder navigieren Sie zu einer <xref:System.Windows.Controls.Page>, Sie können festlegen, die `StartupUri` Attribut im Markup.  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Application.StartupUri%2A> einer eigenständigen Anwendung zum Öffnen einer <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Das folgende Beispiel zeigt, wie Sie mit <xref:System.Windows.Application.StartupUri%2A> aus einer XBAP zum Navigieren zu einer <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Dieses Markup hat denselben Effekt wie der vorherige Code zum Öffnen eines Fensters.  
  
> [!NOTE]
>  Weitere Informationen zur Navigation finden Sie unter [Übersicht über die Navigation](navigation-overview.md).  
  
 Sie behandeln müssen die <xref:System.Windows.Application.Startup> Ereignis zu öffnen eine <xref:System.Windows.Window> , wenn Sie mit einem nicht standardmäßigen Konstruktors instanziieren müssen die Eigenschaften festlegen bzw. Ereignisse abonnieren, bevor es angezeigt werden sollen, oder Sie alle Befehlszeilenargumente verarbeiten müssen, wurden angegeben, wenn die Anwendung gestartet wurde.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Verarbeiten von Befehlszeilenargumenten  
 In Windows können eigenständige Anwendungen von einer Eingabeaufforderung oder dem Desktop gestartet werden. In beiden Fällen können Befehlszeilenargumente an die Anwendung übergeben werden. Im folgenden Beispiel sehen Sie eine Anwendung, die mit nur einem Befehlszeilenargument („/StartMinimized“) gestartet wird:  
  
 `wpfapplication.exe /StartMinimized`  
  
 Während der anwendungsinitialisierung WPF ruft die Befehlszeilenargumente vom Betriebssystem ab und übergibt sie an der <xref:System.Windows.Application.Startup> Ereignishandler über die <xref:System.Windows.StartupEventArgs.Args%2A> Eigenschaft der <xref:System.Windows.StartupEventArgs> Parameter. Mit Code wie dem folgenden können Sie Befehlszeilenargumente abrufen und speichern.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Der Code behandelt <xref:System.Windows.Application.Startup> um zu überprüfen, ob die **/StartMinimized** -Befehlszeilenargument angegeben wurde; Wenn dies der Fall ist, wird es das Hauptfenster mit einer <xref:System.Windows.WindowState> von <xref:System.Windows.WindowState.Minimized>. Beachten Sie, dass die <xref:System.Windows.Window.WindowState%2A> Eigenschaft muss festgelegt werden, programmgesteuert Hauptfenster <xref:System.Windows.Window> muss explizit im Code geöffnet sein.  
  
 XBAPs können nicht abgerufen werden und Befehlszeilenargumente verarbeiten, da sie mit der ClickOnce-Bereitstellung gestartet werden (finden Sie unter [Bereitstellen von WPF-Anwendungen](deploying-a-wpf-application-wpf.md)). Von den zum Starten verwendeten URLs können jedoch Abfragezeichenfolgenparameter abgerufen und verarbeitet werden.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Aktivieren und Deaktivieren von Anwendungen  
 Windows kann Benutzer zwischen Anwendungen zu wechseln. Meistens wird dazu die Tastenkombination ALT+TAB verwendet. Eine Anwendung kann nur gewechselt werden, wenn sie ein sichtbares hat <xref:System.Windows.Window> , die ein Benutzer auswählen kann. Das derzeit ausgewählte <xref:System.Windows.Window> ist die *des aktiven Fensters* (auch bekannt als die *Vordergrundfenster*) und die <xref:System.Windows.Window> , das Benutzereingaben empfängt. Die Anwendung mit dem aktiven Fenster ist die *aktive Anwendung* (oder *vordergrundanwendung*). Eine Anwendung wird unter folgenden Umständen zur aktiven Anwendung:  
  
- Es wird gestartet und zeigt eine <xref:System.Windows.Window>.  
  
- Ein Benutzer wechselt von einer anderen Anwendung durch Auswahl einer <xref:System.Windows.Window> in der Anwendung.  
  
 Sie können erkennen, wenn eine Anwendung aktiv, durch behandeln wird der <xref:System.Windows.Application.Activated?displayProperty=nameWithType> Ereignis.  
  
 Auf ähnliche Weise kann eine Anwendung unter folgenden Umständen inaktiv werden:  
  
- Ein Benutzer wechselt von der aktuellen zu einer anderen Anwendung.  
  
- Wenn die Anwendung heruntergefahren wird.  
  
 Sie können erkennen, wenn eine Anwendung inaktiv, durch behandeln wird der <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> Ereignis.  
  
 Der folgende Code zeigt, wie Sie behandelt die <xref:System.Windows.Application.Activated> und <xref:System.Windows.Application.Deactivated> Ereignisse, um zu bestimmen, ob eine Anwendung aktiv ist.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Ein <xref:System.Windows.Window> auch aktiviert und deaktiviert werden kann. Weitere Informationen finden Sie unter <xref:System.Windows.Window.Activated?displayProperty=nameWithType> und <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Weder <xref:System.Windows.Application.Activated?displayProperty=nameWithType> noch <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> für XBAPs ausgelöst.  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Herunterfahren einer Anwendung  
 Die Lebensdauer einer Anwendung endet mit dem Herunterfahren, das aus folgenden Gründen erfolgen kann:  
  
- Ein Benutzer schließt alle <xref:System.Windows.Window>.  
  
- Ein Benutzer schließt das Haupt- <xref:System.Windows.Window>.  
  
- Der Benutzer beendet die Windows-Sitzung durch abmelden oder Herunterfahren.  
  
- Eine anwendungsspezifische Bedingung wurde erfüllt.  
  
 Können Sie zum Beenden der Anwendung verwalten <xref:System.Windows.Application> bietet die <xref:System.Windows.Application.Shutdown%2A> -Methode, die <xref:System.Windows.Application.ShutdownMode%2A> -Eigenschaft, und die <xref:System.Windows.Application.SessionEnding> und <xref:System.Windows.Application.Exit> Ereignisse.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> kann nur von Anwendungen, die aufgerufen werden <xref:System.Security.Permissions.UIPermission>. Standalone-WPF-Anwendungen verfügen immer über diese Berechtigung. Allerdings gilt dies nicht XBAPs, die in den Sicherheitssandkasten der Internetzone Sicherheit bei teilweiser Vertrauenswürdigkeit ausgeführt.  
  
#### <a name="shutdown-mode"></a>Modus für das Herunterfahren  
 Anwendungen werden in der Regel entweder heruntergefahren, wenn alle Fenster geschlossen werden, oder wenn das Hauptfenster geschlossen wird. Manchmal kann jedoch auch durch andere anwendungsspezifische Bedingungen bestimmt werden, wann eine Anwendung heruntergefahren wird. Sie können angeben, die Bedingungen, unter dem Ihre Anwendung heruntergefahren durch Festlegen von wird <xref:System.Windows.Application.ShutdownMode%2A> mit einem der folgenden <xref:System.Windows.ShutdownMode> -Enumerationswerte fest:  
  
- <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Der Standardwert von <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnLastWindowClose>, d. h., die eine Anwendung automatisch heruntergefahren wird, wenn das letzte Fenster in der Anwendung vom Benutzer geschlossen wird. Aber wenn Ihre Anwendung heruntergefahren werden soll, wenn das Hauptfenster geschlossen wird, WPF automatisch ausgeführt, wenn Sie festlegen, <xref:System.Windows.Application.ShutdownMode%2A> zu <xref:System.Windows.ShutdownMode.OnMainWindowClose>. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Wenn Ihre Bedingungen zum Herunterfahren die anwendungsspezifische können Sie festlegen, <xref:System.Windows.Application.ShutdownMode%2A> zu <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In diesem Fall ist es Ihrer Verantwortung, eine Anwendung heruntergefahren durch explizites Aufrufen der <xref:System.Windows.Application.Shutdown%2A> Methode; andernfalls, Ihre Anwendung weiterhin ausgeführt, auch wenn alle Fenster geschlossen sind. Beachten Sie, dass <xref:System.Windows.Application.Shutdown%2A> wird implizit aufgerufen, wenn die <xref:System.Windows.Application.ShutdownMode%2A> ist entweder <xref:System.Windows.ShutdownMode.OnLastWindowClose> oder <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> eine XBAP festgelegt werden können, aber sie wird ignoriert; eine XBAP wird immer heruntergefahren, wenn die von ihr weg navigiert wird in einem Browser oder beim Schließen des Browsers, die die XBAP hostet. Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md).  
  
#### <a name="session-ending"></a>Beenden einer Sitzung  
 Die Bedingungen zum Herunterfahren, die beschrieben werden die <xref:System.Windows.Application.ShutdownMode%2A> Eigenschaft für eine Anwendung spezifisch sind. In einigen Fällen kann eine Anwendung aber auch als Ergebnis einer externen Bedingung heruntergefahren werden. Die gängigste externe Bedingung tritt auf, wenn ein Benutzer die Windows-Sitzung durch die folgenden Aktionen beendet:  
  
- Abmelden  
  
- Herunterfahren  
  
- Neustarten  
  
- Wechseln in den Ruhezustand  
  
 Um zu erkennen, wenn eine Windows-Sitzung beendet wird, können Sie behandeln die <xref:System.Windows.Application.SessionEnding> Ereignis, wie im folgenden Beispiel dargestellt.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In diesem Beispiel überprüft der Code die <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> Eigenschaft, um zu bestimmen, wie die Windows-Sitzung beendet wird. Dieser Wert wird verwendet, um dem Benutzer eine Bestätigungsmeldung anzuzeigen. Der Code legt fest, wenn der Benutzer nicht die Sitzung beenden möchte, <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> zu `true` um zu verhindern, dass die Windows-Sitzung beendet.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> für XBAPs wird nicht ausgelöst werden.

#### <a name="exit"></a>Schließen  
 Beim Herunterfahren einer Anwendung werden evtl. abschließende Verarbeitungsaufgaben ausgeführt, z. B. Beibehalten des Anwendungszustands. In diesen Situationen können Sie behandeln die <xref:System.Windows.Application.Exit> -Ereignis, als die `App_Exit` -Ereignishandler wird im folgenden Beispiel. Es wird definiert, wie ein Ereignishandler in der *"App.xaml"* Datei. Die Implementierung wird hervorgehoben, der *"App.Xaml.cs"* und *"Application.Xaml.vb"* Dateien.
  
[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]  
  
 [!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
 [!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]  
  
 Das vollständige Beispiel finden Sie unter [beibehalten und Wiederherstellen mit Anwendungsbereich Eigenschaften über mehrere Anwendungssitzungen](persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> kann von sowohl eigenständigen Anwendungen als auch XBAPs behandelt werden. Für XBAPs <xref:System.Windows.Application.Exit> wird ausgelöst, wenn Sie in den folgenden Situationen:  
  
- Eine XBAP ist weg navigiert.  
  
- In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], wenn die Registerkarte, die die XBAP gehostet wird geschlossen ist.  
  
- Wenn der Browser geschlossen wird.  
  
#### <a name="exit-code"></a>Exitcode  
 Anwendungen werden meistens durch das Betriebssystem als Reaktion auf eine Benutzeranforderung gestartet. Eine Anwendung kann aber auch von einer anderen Anwendung gestartet werden, um eine bestimmte Aufgabe zu übernehmen. Wenn die gestartete Anwendung heruntergefahren wird, muss die startende Anwendung möglicherweise über die Bedingung informiert werden, unter der die gestartete Anwendung heruntergefahren wurde. In diesen Fällen kann Windows Anwendungen einen Anwendungsexitcode zurückzugeben. Standardmäßig geben die WPF-Anwendungen Exitcodewert 0 zurück.  
  
> [!NOTE]
>  Beim Debuggen in Visual Studio wird ein Exitcode der Anwendung angezeigt, der **Ausgabe** Fenster, wenn die Anwendung in einer Meldung heruntergefahren, der folgendermaßen aussieht:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Öffnen Sie die **Ausgabe** Fenster, indem Sie auf **Ausgabe** auf die **Ansicht** Menü.  
  
 Um den Exitcode ändern möchten, können Sie rufen die <xref:System.Windows.Application.Shutdown%28System.Int32%29> überladen ist, wird ein ganzzahliges Argument zum Exitcode akzeptiert:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Sie können den Wert des Exitcodes ermitteln und ändern, indem die Behandlung der <xref:System.Windows.Application.Exit> Ereignis. Die <xref:System.Windows.Application.Exit> -Ereignishandler übergeben wird ein <xref:System.Windows.ExitEventArgs> dem ermöglicht den Zugriff auf den Exitcode mit der <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Sie können den Exitcode sowohl von eigenständigen Anwendungen als auch XBAPs in festlegen. Der Exitcodewert wird jedoch für XBAPs ignoriert.  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Nicht behandelte Ausnahmen  
 Es kommt vor, dass eine Anwendung unter nicht ordnungsgemäßen Bedingungen heruntergefahren wird, z. B. wenn eine unerwartete Ausnahme ausgelöst wird. In diesem Fall verfügt die Anwendung möglicherweise nicht über den Code, der zum Erkennen und Verarbeiten der Ausnahme erforderlich ist. Eine solche Ausnahme wird als nicht behandelte Ausnahme bezeichnet. Vor dem Schließen der Anwendung wird eine Meldung angezeigt, die der folgenden ähnelt.  
  
 ![Screenshot mit einer Benachrichtigung über Ausnahmefehler.](./media/application-management-overview/unhandled-exception-notification.png)  
  
 Für die Benutzererfahrung ist es vorteilhafter, wenn eine Anwendung dieses Standardverhalten vermeidet. Dazu dienen mehrere oder alle der folgenden Aktionen:  
  
- Anzeigen von benutzerfreundlichen Informationen  
  
- Versuchen, eine Anwendung weiterhin auszuführen  
  
- Aufzeichnen von detaillierten, entwicklerfreundlichen-Ausnahmeinformationen in die Windows-Ereignisprotokoll.  
  
 Implementierung dieser Unterstützung hängt von der nicht behandelte Ausnahmen zu erkennen, d. h. die <xref:System.Windows.Application.DispatcherUnhandledException> -Ereignis wird für ausgelöst.  
  
[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]  
  
 Die <xref:System.Windows.Application.DispatcherUnhandledException> übergebene Ereignishandler wird ein <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> Parameter, der Kontextinformationen zur nicht behandelten Ausnahme, einschließlich der Ausnahme selbst enthält (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Sie können anhand dieser Informationen feststellen, wie die Ausnahme behandelt werden soll.  
  
 Bei der Behandlung <xref:System.Windows.Application.DispatcherUnhandledException>, legen Sie die <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> Eigenschaft `true`ist, andernfalls WPF immer noch berücksichtigt die Ausnahme unbehandelt und wird auf die zuvor beschriebene Standardverhalten zurückgesetzt. Wenn eine nicht behandelte Ausnahme ausgelöst wird und entweder die <xref:System.Windows.Application.DispatcherUnhandledException> -Ereignis nicht behandelt wird oder das Ereignis behandelt wird und <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> nastaven NA hodnotu `false`, die Anwendung sofort heruntergefahren. Darüber hinaus keine weiteren <xref:System.Windows.Application> Ereignisse ausgelöst werden. Folglich müssen Sie behandeln <xref:System.Windows.Application.DispatcherUnhandledException> , wenn Ihre Anwendung über Code, die ausgeführt werden muss verfügt, bevor die Anwendung beendet wird.  
  
 Obwohl eine Anwendung wegen einer nicht behandelten Ausnahme heruntergefahren werden kann, erfolgt das Herunterfahren normalerweise als Reaktion auf eine Benutzeranforderung, wie im nächsten Abschnitt beschrieben.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Anwendungslebensdauer-Ereignisse  
 Eigenständige Anwendungen als auch XBAPs haben nicht genau dieselbe Lebensdauer. Die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer eigenständigen Anwendung und die Reihenfolge, in der sie ausgelöst werden.  
  
 ![Eigenständige Anwendung &#45; Anwendungsobjektereignisse](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Ebenso wird die folgende Abbildung veranschaulicht die wichtigsten Ereignisse in der Lebensdauer einer XBAP und zeigt die Reihenfolge, in der sie ausgelöst werden.  
  
 ![XBAP &#45; Anwendungsobjektereignisse](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Application>
- [Übersicht über WPF-Fenster](wpf-windows-overview.md)
- [Übersicht über die Navigation](navigation-overview.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](wpf-application-resource-content-and-data-files.md)
- [Paket-URI in WPF](pack-uris-in-wpf.md)
- [Anwendungsmodell: Gewusst-wie-Themen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Anwendungsentwicklung](index.md)
