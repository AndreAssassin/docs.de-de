---
title: Workflowüberwachung
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: cd53ed834fdacb639b38346dca831ef4c3e26337
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321665"
---
# <a name="workflow-tracing"></a>Workflowüberwachung
Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework-Ablaufverfolgungslistenern zu erfassen. Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist. Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows. Sie können sie mit der Ereignisablaufverfolgung (ETW) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Aktivieren der Debugablaufverfolgung in ETW  
 Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:  
  
1. Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.  
  
2. In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >**. Mit der rechten Maustaste **Anwendungsserver-Anwendungen** , und wählen Sie **Ansicht-analytische und Debugprotokolle**. Mit der rechten Maustaste **Debuggen** , und wählen Sie **Protokoll aktivieren**.  
  
3. Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen. Navigieren Sie zu **Ereignisanzeige -> Anwendungen und Dienstprotokolle > Microsoft -> Windows-Anwendungsserver-Anwendungen >**. Mit der rechten Maustaste **Debuggen** , und wählen Sie **aktualisieren**.  
  
4. Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes (KB). Es wird empfohlen, die Größe auf 32 KB zu erweitern. Gehen Sie hierzu folgendermaßen vor.  
  
    1.  Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  Ändern der \<BufferSize >-Wert in der Datei "Windows.ApplicationServer.Applications.man" auf 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  Wenn Sie die .NET Framework 4 Client Profile verwenden, müssen Sie zuerst das ETW-Manifest registrieren, mithilfe des folgenden Befehls aus dem .NET Framework 4-Verzeichnis: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Aktivieren der Debugablaufverfolgung mit System.Diagnostics  
 Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt. In diesem Beispiel eine [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) konfiguriert, um Ablaufverfolgungsinformationen in die Datei MyTraceLog.txt im aktuellen Verzeichnis zu speichern.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Windows Server App Fabric-Überwachung](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Überwachen von Anwendungen mit AppFabric](https://go.microsoft.com/fwlink/?LinkId=201275)
