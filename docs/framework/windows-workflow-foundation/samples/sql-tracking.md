---
title: SQL-Nachverfolgung
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: f3c48b40e2d3d7dec2b9008b3de738f9b2983610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785917"
---
# <a name="sql-tracking"></a>SQL-Nachverfolgung
In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter SQL-Nachverfolgungsteilnehmer, der Nachverfolgungsdatensätze in eine SQL-Datenbank schreibt, geschrieben wird. Windows Workflow Foundation (WF) stellt die workflownachverfolgung um Einblick in die Ausführung einer Workflowinstanz zu erhalten. Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus. Weitere Informationen zur workflownachverfolgung finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../workflow-tracking-and-tracing.md).

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben. In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express-Instanz verwendet wird. Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.

2. Erstellen Sie die SQL Server-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis (\WF\Basic\Tracking\SqlTracking\CS\Scripts) ausführen. Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.

    > [!NOTE]
    >  Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express. Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".  
  
3. Öffnen Sie "sqltrackingsample.sln" in Visual Studio 2010 ein.  
  
4. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5. Drücken Sie F5, um die Anwendung auszuführen.  
  
     Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.  
  
6. Klicken Sie im Browser auf "StockPriceService.xamlx".  
  
7. Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält. Kopieren Sie diese Adresse.  
  
     Ein Beispiel für die WSDL-Adresse des lokalen Diensts ist `http://localhost:65193/StockPriceService.xamlx?wsdl`.  
  
8. Führen Sie den WCF-Testclient (WcfTestClient.exe) über [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] aus. Er befindet im Verzeichnis "Microsoft Visual Studio 10.0 \Common7\IDE".  
  
9. Klicken Sie in der WCF-Testclient auf die **Datei** Menü **Dienst hinzufügen**. Fügen Sie die lokale Dienstadresse in das Textfeld ein. Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
10. Klicken Sie in der WCF-Testclient, doppelklicken auf **GetStockPrice**. Daraufhin wird die `GetStockPrice` Vorgang, einen Parameter, geben Sie den Wert `Contoso` , und klicken Sie auf **Invoke**.  
  
11. Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL-Datenbank geschrieben. Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen. Weitere Informationen zu SQL Server Management Studio, finden Sie unter [Einführung in SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express kann heruntergeladen werden [hier](https://go.microsoft.com/fwlink/?LinkId=180520). Durch Ausführen einer Select-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.  
  
#### <a name="to-uninstall-the-sample"></a>So installieren Sie das Beispiel aus  
  
1. Führen Sie das Skript "Tdrackingcleanup.cmd" im Beispielverzeichnis (\WF\Basic\Tracking\SqlTracking) aus.  
  
    > [!NOTE]
    >  "Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen. Wenn Sie eine andere SQL Server-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
