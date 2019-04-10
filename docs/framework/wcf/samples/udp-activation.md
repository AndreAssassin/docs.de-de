---
title: UDP-Aktivierung
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: 6e19e92872c9b9344db7e787f0cd77e0a315f1a0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337655"
---
# <a name="udp-activation"></a>UDP-Aktivierung
Dieses Beispiel basiert auf der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel. Es erweitert die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel zur Unterstützung von prozessaktivierung mittels der Windows Process Activation Service (WAS).  
  
 Das Beispiel besteht im Wesentlichen aus drei Teilen:  
  
-   Einem UDP-Protokoll-Aktivierer, welcher ein eigenständiger Prozess ist, der für zu aktivierende Anwendungen UDP-Nachrichten empfängt.  
  
-   Einem Client, der mit dem benutzerdefinierten UDP-Transport Nachrichten sendet.  
  
-   Einem Dienst, der in einem von WAS aktivierten Workerprozess gehostet wird und Nachrichten über den benutzerdefinierten UDP-Transport empfängt.  
  
## <a name="udp-protocol-activator"></a>UDP-Protokoll-Aktivierer  
 Die UDP-Protokoll-Aktivierer ist eine Brücke zwischen dem WCF-Client und der WCF-Dienst. Er bietet Datenkommunikation über das UDP-Protokoll auf der Transportebene. Seine zwei Hauptfunktionen sind:  
  
-   WAS-Listeneradapter (LA), der mit WAS zusammenarbeitet, um als Antwort auf eingehende Nachrichten Prozesse zu aktivieren.  
  
-   UDP-Protokolllistener, der für zu aktivierende Anwendungen UDP-Nachrichten entgegennimmt.  
  
 Der Aktivierer muss auf dem Server als eigenständiges Programm ausgeführt werden. WAS-Listeneradapter (wie der NetTcpActivator und der NetPipeActivator) werden meist in Windows-Diensten mit langer Laufzeit implementiert. Im vorliegenden Beispiel wird der Protokollaktivierer aber aus Gründen der Einfachheit und Übersichtlichkeit als eigenständige Anwendung implementiert.  
  
### <a name="was-listener-adapter"></a>WAS-Listeneradapter  
 Der WAS-Listeneradapter für UDP ist in der `UdpListenerAdapter`-Klasse implementiert. Das ist das Modul, das mit WAS interagiert, um Anwendungen für das UDP-Protokoll zu aktivieren. Dies erfolgt durch Aufrufen der folgenden Webhost-APIs:  
  
-   `WebhostRegisterProtocol`  
  
-   `WebhostUnregisterProtocol`  
  
-   `WebhostOpenListenerChannelInstance`  
  
-   `WebhostCloseAllListenerChannelInstances`  
  
 Nach dem ersten Aufrufen von `WebhostRegisterProtocol` empfängt der Listeneradapter den `ApplicationCreated`-Rückruf von WAS für alle in applicationHost.config (die sich unter %windir%\system32\inetsrv befindet) registrierten Anwendungen. In diesem Beispiel werden nur die Anwendungen mit aktiviertem UDP-Protokoll verarbeitet (mit der Protokoll-ID als "net.udp"). In anderen Implementierungen kann dies anders gehalten werden, wenn diese Implementierungen auf dynamische Konfigurationsänderungen bei der Anwendung reagieren (wie zum Beispiel der Übergang einer Anwendung von aktiviert zu deaktiviert).  
  
 Wenn der `ConfigManagerInitializationCompleted`-Rückruf empfangen wird, zeigt dies an, dass WAS sämtliche Benachrichtigungen für die Initialisierung des Protokolls abgeschlossen hat. Ab diesem Zeitpunkt ist der Listeneradapter bereit, Aktivierungsanforderungen zu verarbeiten.  
  
 Wenn eine neue Anforderung für eine Anwendung zum ersten Mal eingeht, ruft der Listeneradapter `WebhostOpenListenerChannelInstance` in WAS auf, wodurch der Workerprozess gestartet wird (wenn er nicht bereits gestartet ist). Anschließend werden die Protokollhandler geladen, und die Kommunikation zwischen dem Listeneradapter und der virtuellen Anwendung kann beginnen.  
  
 Der Listeneradapter wird in der %SystemRoot%\System32\inetsrv\ApplicationHost.config in registriert die <`listenerAdapters`> im Abschnitt wie folgt:  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a>Protokolllistener  
 Der UDP-Protokolllistener ist ein Modul innerhalb des Protokollaktivierers, der für die virtuelle Anwendung einen UDP-Endpunkt überwacht. Er ist in der `UdpSocketListener`-Klasse implementiert. Der Endpunkt liegt als `IPEndpoint` vor, bei dem die Portnummer aus der Bindung des Protokolls für die Site extrahiert wird.  
  
### <a name="control-service"></a>Steuerungsdienst  
 In diesem Beispiel verwenden wir WCF für die Kommunikation zwischen dem Aktivierer und die WAS-Workerprozess. Der Dienst, der sich im Aktivierer befindet, wird als "Steuerungsdienst" bezeichnet.  
  
## <a name="protocol-handlers"></a>Protokollhandler  
 Nachdem der Listeneradapter `WebhostOpenListenerChannelInstance` aufgerufen hat, startet der WAS-Prozess-Manager den Workerprozess (falls dieser noch nicht gestartet ist). Anschließend lädt der im Workerprozess befindliche Anwendungs-Manager den UDP-Prozessprotokollhandler (PPH) mit der Anforderung nach dieser `ListenerChannelId`. Der PPH wiederum ruft `IAdphManager`.`StartAppDomainProtocolListenerChannel` um die UDP-AppDomain-Protokollhandler (ADPH) zu starten.  
  
## <a name="hostedudptransportconfiguration"></a>HostedUDPTransportConfiguration  
 Diese Informationen werden wie folgt in der Web.config registriert:  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a>Spezielle Einrichtung für dieses Beispiel  
 Dieses Beispiel kann nur unter Windows Vista, Windows Server 2008 oder Windows 7 erstellt und ausgeführt werden. Zum Ausführen des Beispiels müssen Sie zuerst sämtliche Komponenten ordnungsgemäß einrichten. Gehen Sie folgendermaßen vor, um das Beispiel zu installieren.  
  
#### <a name="to-set-up-this-sample"></a>So richten Sie dieses Beispiel ein  
  
1. Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Erstellen Sie das Projekt unter Windows Vista. Nach dem Kompilieren führt es in der Postbuildphase auch die folgenden Vorgänge aus:  
  
    -   Es installiert die UDP-Bindung für die Site „Default Web Site“.  
  
    -   Es erstellt den "ServiceModelSamples" der virtuellen Anwendung so, dass er auf den physischen Pfad zeigt: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".  
  
    -   Außerdem aktiviert es für diese virtuelle Anwendung das "net.udp"-Protokoll.  
  
3. Starten Sie die Benutzeroberflächenanwendung "WasNetActivator.exe". Klicken Sie auf die **Setup** , überprüfen Sie die folgenden Kontrollkästchen und klicken Sie dann auf **installieren** , diese zu installieren:  
  
    -   UDP-Listeneradapter  
  
    -   UDP-Protokollhandler  
  
4. Klicken Sie auf die **Aktivierung** Registerkarte die Benutzeroberflächenanwendung "WasNetActivator.exe". Klicken Sie auf die **starten** Schaltfläche, um den Listeneradapter zu starten. Nun können Sie das Programm ausführen.  
  
    > [!NOTE]
    >  Wenn Sie die Arbeit mit diesem Beispiel abgeschlossen haben, müssen Sie Cleanup.bat ausführen, um die net.udp-Bindung aus der „Default Web Site“ zu entfernen.  
  
## <a name="sample-usage"></a>Verwendung des Beispiels  
 Nach dem Kompilieren liegen vier verschiedene Binärdateien vor:  
  
-   Client.exe: Der Clientcode. Die App.config ist in die Client.exe-Clientkonfigurationsdatei hinein kompiliert.  
  
-   UDPActivation.dll: Die Bibliothek, die alle wichtigen UDP-Implementierungen enthält.  
  
-   Service.dll: Der Dienstcode. Diese wird in das Verzeichnis \bin der virtuellen Anwendung ServiceModelSamples kopiert. Die Dienstdatei ist Service.svc, und die Konfigurationsdatei ist Web.config. Nach dem Kompilieren werden sie an den folgenden Speicherort kopiert: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.  
  
-   WasNetActivator: Die UDP-aktiviererprogramm.  
  
-   Stellen Sie sicher, dass alle erforderlichen Bestandteile ordnungsgemäß installiert sind. Die folgenden Schritte zeigen, wie das Beispiel ausgeführt wird:  
  
1. Stellen Sie sicher, dass die folgenden Windows-Dienste gestartet sind:  
  
    -   WAS (Windows Process Activation Service)  
  
    -   Internetinformationsdienste (IIS): W3SVC.  
  
2. Starten Sie anschließend den Aktivierer (WasNetActivator.exe). Unter den **Aktivierung** Registerkarte, die das einzige Protokoll, **UDP**, in der Dropdownliste ausgewählt ist. Klicken Sie auf die **starten** Schaltfläche, um den Aktivierer zu starten.  
  
3. Wenn der Aktivierer gestartet ist, können Sie den Clientcode ausführen, indem Sie in einem Befehlsfenster die Client.exe ausführen. Nachfolgend ist die Ausgabe des Beispiels aufgeführt:  
  
    ```  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
