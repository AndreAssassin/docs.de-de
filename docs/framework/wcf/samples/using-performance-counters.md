---
title: Verwenden von Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 724580c1725cf6513e1d85f03b0abfdefb4d040a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044534"
---
# <a name="using-performance-counters"></a><span data-ttu-id="ad2e0-102">Verwenden von Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="ad2e0-102">Using Performance Counters</span></span>
<span data-ttu-id="ad2e0-103">In diesem Beispiel wird veranschaulicht, wie auf Windows Communication Foundation (WCF)-Leistungsindikatoren zugegriffen wird und wie benutzerdefinierte Leistungsindikatoren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="ad2e0-104">Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad2e0-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ad2e0-106">In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`-Diensts auf.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="ad2e0-107">Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="ad2e0-108">Der Dienst bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="ad2e0-109">Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ad2e0-110">Diese Aufgabe kann auch mit dem Konfigurations- [Editor-Tool (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="ad2e0-111">Wenn Leistungsindikatoren aktiviert sind, wird die gesamte Sammlung von WCF-Leistungsindikatoren für den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="ad2e0-112">.NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="ad2e0-113">Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="ad2e0-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ad2e0-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ad2e0-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ad2e0-115">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ad2e0-116">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ad2e0-117">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ad2e0-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="ad2e0-118">So zeigen Sie Leistungsdaten an</span><span class="sxs-lookup"><span data-stu-id="ad2e0-118">To view performance data</span></span>  
  
1. <span data-ttu-id="ad2e0-119">Starten Sie das System Monitor Tool, indem Sie auf **Start**, **ausführen...** , eingeben und auf OK klicken `perfmon` **,** oder wählen Sie in der Systemsteuerung die Option **Verwaltung** aus, und doppelklicken Sie auf **Leistung**.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad2e0-120">Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="ad2e0-121">Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="ad2e0-122">Fügen Sie WCF-Indikatoren hinzu, indem Sie mit der rechten Maustaste auf den Diagrammbereich klicken und **Zähler hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="ad2e0-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="ad2e0-123">Wählen Sie im Dialogfeld Leistungsindikatoren **Hinzufügen** im Dropdown-Listenfeld Leistungs Objekt die Option **Service Model Operation 3.0.0.0, Service Model Endpoint 3.0.0.0 oder Service Model Service 3.0.0.0** aus.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="ad2e0-124">Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad2e0-125">Es sind keine WCF-Leistungsindikatoren für einen Dienst vorhanden, wenn auf dem Computer keine WCF-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="ad2e0-126">So aktivieren Sie Indikatoren mit dem Konfigurations-Editor</span><span class="sxs-lookup"><span data-stu-id="ad2e0-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="ad2e0-127">Öffnen Sie eine Instanz von SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="ad2e0-128">Klicken Sie im Menü Datei auf **Öffnen** , und klicken Sie dann auf **Konfigurationsdatei...** .</span><span class="sxs-lookup"><span data-stu-id="ad2e0-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="ad2e0-129">Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".</span><span class="sxs-lookup"><span data-stu-id="ad2e0-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="ad2e0-130">Klicken Sie in der Konfigurations Struktur auf **Diagnose** .</span><span class="sxs-lookup"><span data-stu-id="ad2e0-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="ad2e0-131">**Wechseln Sie im** **Diagnose** Fenster zum Anzeigen von "alle".</span><span class="sxs-lookup"><span data-stu-id="ad2e0-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="ad2e0-132">Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ad2e0-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ad2e0-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-134">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ad2e0-135">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad2e0-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ad2e0-136">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="ad2e0-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad2e0-137">See also</span></span>

- [<span data-ttu-id="ad2e0-138">AppFabric-Überwachungs Beispiele</span><span class="sxs-lookup"><span data-stu-id="ad2e0-138">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
