---
title: Zirkuläre Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: cd1a0c85dd42a7f064e75c7efdacb9ea46ef445d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303959"
---
# <a name="circular-tracing"></a>Zirkuläre Ablaufverfolgung
Dieses Beispiel veranschaulicht die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners. Ein gängiges Szenario bei Produktionsdiensten besteht darin, dass Dienste vorhanden sind, die für längere Zeiträume verfügbar sind, und dass die Ablaufverfolgung auf einer unteren Ebene aktiviert ist. Diese Dienste belegen viel Speicherplatz. Bei der Problembehandlung sind zum Lösen eines Problems bei einem Dienst die aktuellsten Daten aus dem Ablaufverfolgungsprotokoll relevant. Dieses Beispiel zeigt die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners, bei der nur die neuesten Ablaufverfolgungen bis zu einer zu konfigurierenden Datenmenge auf der Festplatte aufbewahrt werden. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und einen benutzerdefinierten Ablaufverfolgungslistener enthält.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie kennen die [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel und Leseberechtigungen für die Dokumentation für die [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel.  
  
## <a name="circular-buffer-trace-listener"></a>Zirkulärer Puffer-Ablaufverfolgungslistener  
 Die Implementierung des zirkulären Puffer-Ablaufverfolgungslisteners beruht auf dem Konzept, dass zwei Dateien vorhanden sind, von denen jede bis zur Hälfte der gewünschten Ablaufverfolgungsprotokolldaten speichern kann. Der Listener erstellt eine Datei und schreibt in diese, bis sie den Grenzwert der halben Datengröße erreicht. Dann wechselt der Listener zu einer zweiten Datei. Wenn der Listener den Grenzwert bei der zweiten Datei erreicht, überschreibt er die erste Datei mit neuen Ablaufverfolgungen.  
  
 Dieser Listener leitet sich von der `XmlWriteTraceListener` und ermöglicht es die Protokolle angezeigt werden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Beim Anzeigen der Protokolle können die beiden Protokolldateien leicht rekombiniert werden, indem man beide Protokolldateien gleichzeitig im Service Trace Viewer öffnet. Der Service Trace Viewer erledigt automatisch das Sortieren der Ablaufverfolgungen, so dass diese in der korrekten Reihenfolge angezeigt werden.  
  
## <a name="configuration"></a>Konfiguration  
 Durch Hinzufügen des folgenden Codes für einen Listener und Quellelemente kann ein Dienst zum Verwenden des zirkulären Puffer-Ablaufverfolgungslisteners konfiguriert werden. Die maximale Dateigröße wird durch Angeben des `maxFileSizeKB`-Attributs in der Konfiguration des zirkulären Ablaufverfolgungslisteners festlegt. Dies wird im folgenden Code demonstriert.  
  
```xml  
<system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">  
      <listeners>  
        <add name="CircularTraceListener" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"   
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
