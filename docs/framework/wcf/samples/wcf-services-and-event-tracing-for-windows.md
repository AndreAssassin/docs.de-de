---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 35d0202a3b9cf4060240dc521554644d419a5c23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723172"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="203d7-102">WCF-Dienste und Ereignisablaufverfolgung für Windows</span><span class="sxs-lookup"><span data-stu-id="203d7-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="203d7-103">In diesem Beispiel wird veranschaulicht, wie die analytische Ablaufverfolgung in Windows Communication Foundation (WCF) verwendet, um Ereignisse im Event Tracing for Windows (ETW) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="203d7-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="203d7-104">Die analytische Ablaufverfolgung werden Ereignisse an wichtigen Punkten im WCF-Stapel, mit denen die Problembehandlung für die WCF-Dienste in der produktionsumgebung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="203d7-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="203d7-105">Analytische Ablaufverfolgung in WCF-Dienste ist, die die Ablaufverfolgung kann aktiviert werden in einer produktionsumgebung mit minimalen Auswirkungen auf die Leistung.</span><span class="sxs-lookup"><span data-stu-id="203d7-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="203d7-106">Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="203d7-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="203d7-107">Dieses Beispiel enthält einen grundlegenden WCF-Dienst in dem Ereignisse aus dem Dienst in das Ereignisprotokoll ausgegeben werden die mithilfe der Ereignisanzeige angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="203d7-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="203d7-108">Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die für Ereignisse, die vom WCF-Dienst lauscht.</span><span class="sxs-lookup"><span data-stu-id="203d7-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="203d7-109">Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="203d7-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="203d7-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="203d7-110">To use this sample</span></span>

1. <span data-ttu-id="203d7-111">Öffnen Sie mit Visual Studio 2012 die EtwAnalyticTraceSample.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="203d7-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="203d7-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="203d7-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="203d7-113">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="203d7-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="203d7-114">Klicken Sie im Webbrowser auf **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="203d7-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="203d7-115">Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="203d7-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="203d7-116">Kopieren Sie diesen URI.</span><span class="sxs-lookup"><span data-stu-id="203d7-116">Copy that URI.</span></span>

     <span data-ttu-id="203d7-117">In der Standardeinstellung der Dienst gestartet wird Lauscht auf Anforderungen auf Port 1378 `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="203d7-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="203d7-118">Führen Sie den WCF-Testclient (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="203d7-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="203d7-119">WCF-Testclient (WcfTestClient.exe) befindet sich unter `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="203d7-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="203d7-120">Der standardmäßige Visual Studio 2012 ist `C:\Program Files\Microsoft Visual Studio 10.0`.</span><span class="sxs-lookup"><span data-stu-id="203d7-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="203d7-121">Fügen Sie innerhalb der WCF-Testclient den Dienst dazu **Datei**, und klicken Sie dann **Dienst hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="203d7-122">Fügen Sie die Endpunktadresse im Eingabefeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="203d7-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="203d7-123">Die Standardeinstellung ist `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="203d7-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="203d7-124">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="203d7-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="203d7-125">Vor dem Aufrufen des Diensts die Ereignisanzeige starten, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom WCF-Dienst ausgegebene Überwachungsereignisse ausführt.</span><span class="sxs-lookup"><span data-stu-id="203d7-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="203d7-126">Von der **starten** , wählen Sie im Menü **Verwaltung**, und klicken Sie dann **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="203d7-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="203d7-127">Aktivieren der **analytisch** und **Debuggen** Protokolle.</span><span class="sxs-lookup"><span data-stu-id="203d7-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="203d7-128">In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="203d7-129">Mit der rechten Maustaste **Anwendungsserver-Anwendungen**Option **Ansicht**, und klicken Sie dann **analytische und Debugprotokolle**.</span><span class="sxs-lookup"><span data-stu-id="203d7-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="203d7-130">Sicherstellen, dass die **analytische und Debugprotokolle** Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="203d7-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="203d7-131">Aktivieren der **analytisch** Protokoll.</span><span class="sxs-lookup"><span data-stu-id="203d7-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="203d7-132">In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="203d7-133">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="203d7-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="203d7-134">So testen Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="203d7-134">To test the service</span></span>

1. <span data-ttu-id="203d7-135">Wechseln Sie zurück zum WCF-Testclient, und doppelklicken Sie auf `Divide` und halten Sie die Standardwerte, die als Nenner 0 angeben.</span><span class="sxs-lookup"><span data-stu-id="203d7-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="203d7-136">Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="203d7-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="203d7-137">Beachten Sie die vom Dienst ausgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="203d7-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="203d7-138">Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="203d7-139">Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="203d7-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="203d7-140">Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="203d7-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="203d7-141">Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="203d7-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="203d7-142">Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben.</span><span class="sxs-lookup"><span data-stu-id="203d7-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="203d7-143">Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.</span><span class="sxs-lookup"><span data-stu-id="203d7-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="203d7-144">Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="203d7-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="203d7-145">Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="203d7-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="203d7-146">So führen Sie eine (optionale) Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="203d7-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="203d7-147">Öffnen Sie die Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="203d7-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="203d7-148">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="203d7-149">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="203d7-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="203d7-150">Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="203d7-151">Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.</span><span class="sxs-lookup"><span data-stu-id="203d7-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="203d7-152">Wählen Sie die **löschen** Option aus, um die Ereignisse zu löschen.</span><span class="sxs-lookup"><span data-stu-id="203d7-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="203d7-153">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="203d7-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="203d7-154">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="203d7-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="203d7-155">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="203d7-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="203d7-156">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="203d7-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="203d7-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="203d7-157">See also</span></span>

- [<span data-ttu-id="203d7-158">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="203d7-158">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
