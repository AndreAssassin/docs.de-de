---
title: Erweitern der Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c56f886857e8d391a243e3af4a13353f14116247
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990144"
---
# <a name="extending-tracing"></a><span data-ttu-id="67ff1-102">Erweitern der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="67ff1-102">Extending Tracing</span></span>
<span data-ttu-id="67ff1-103">In diesem Beispiel wird veranschaulicht, wie die Ablaufverfolgungsfunktion von Windows Communication Foundation (WCF) zu erweitern, indem Sie das Schreiben von benutzerdefinierten aktivitätsablaufverfolgungen im Client- und Dienstcode.</span><span class="sxs-lookup"><span data-stu-id="67ff1-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="67ff1-104">Dies ermöglicht es dem Benutzer, Ablaufverfolgungsaktivitäten zu erstellen und Ablaufverfolgungen in logischen Arbeitseinheiten zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="67ff1-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="67ff1-105">Es ist auch möglich, Aktivitäten über Übertragungen (innerhalb desselben Endpunkts) und Weitergabe (über verschiedene Endpunkte) zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="67ff1-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="67ff1-106">In diesem Beispiel wird Ablaufverfolgung sowohl für den Client als auch den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="67ff1-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="67ff1-107">Weitere Informationen zum Aktivieren der Ablaufverfolgung in Client und Dienst-Konfigurationsdateien finden Sie unter [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="67ff1-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="67ff1-108">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="67ff1-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ff1-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="67ff1-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="67ff1-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="67ff1-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="67ff1-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="67ff1-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="67ff1-112">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="67ff1-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="67ff1-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="67ff1-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="67ff1-114">Ablaufverfolgung und Aktivitätsweitergabe</span><span class="sxs-lookup"><span data-stu-id="67ff1-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="67ff1-115">Eine benutzerdefinierte aktivitätsablaufverfolgung kann der Benutzer eigene ablaufverfolgungsaktivitäten auf Gruppe ablaufverfolgungen in logische Arbeitseinheiten zu erstellen, Aktivitäten über Übertragungen und Weitergabe zu korrelieren und die Leistungskosten der WCF-Ablaufverfolgung (z. B. den Speicherplatz, die Kosten eine Protokolldatei).</span><span class="sxs-lookup"><span data-stu-id="67ff1-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="67ff1-116">Hinzufügen benutzerdefinierter Quellen</span><span class="sxs-lookup"><span data-stu-id="67ff1-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="67ff1-117">Benutzerdefinierte Ablaufverfolgungen können sowohl zu Client- als auch Dienstcode hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="67ff1-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="67ff1-118">Hinzufügen von Ablaufverfolgungsquellen an den Client oder Dienst-Konfigurationsdateien ermöglichen, diese benutzerdefinierten ablaufverfolgungen aufgezeichnet und angezeigt wird, der [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="67ff1-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="67ff1-119">Der folgende Code zeigt, wie der Konfigurationsdatei eine benutzerdefinierte Ablaufverfolgungsquelle namens `ServerCalculatorTraceSource` hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="67ff1-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="67ff1-120">Korrelieren von Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="67ff1-120">Correlating Activities</span></span>  
 <span data-ttu-id="67ff1-121">Zum Korrelieren von Aktivitäten direkt zwischen Endpunkten muss für das `propagateActivity`-Attribut in der `true`-Ablaufverfolgungsquelle der Wert `System.ServiceModel` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="67ff1-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="67ff1-122">Darüber hinaus müssen um ablaufverfolgungen weiterzugeben, ohne Umweg über WCF-Aktivitäten, ServiceModel-Aktivitätsablaufverfolgung deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="67ff1-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="67ff1-123">Dies ist im folgenden Codebeispiel zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="67ff1-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ff1-124">Das Deaktivieren von ServiceModel-Aktivitätsablaufverfolgung ist nicht dasselbe, wie die von der `switchValue`-Eigenschaft angegebene Ablaufverfolgungsebene zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="67ff1-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="67ff1-125">Verringern von Leistungskosten</span><span class="sxs-lookup"><span data-stu-id="67ff1-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="67ff1-126">Wenn `ActivityTracing` in der `System.ServiceModel`-Ablaufverfolgungsquelle ausgeschaltet wird, wird eine Ablaufverfolgungsdatei erstellt, die nur benutzerdefinierte Aktivitätsablaufverfolgungen, jedoch keine der ServiceModel-Aktivitätsablaufverfolgungen enthält.</span><span class="sxs-lookup"><span data-stu-id="67ff1-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="67ff1-127">Dadurch wird die Protokolldatei deutlich kleiner.</span><span class="sxs-lookup"><span data-stu-id="67ff1-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="67ff1-128">Allerdings ist die Möglichkeit zum Korrelieren von WCF, die Verarbeitung von ablaufverfolgungen verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="67ff1-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="67ff1-129">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="67ff1-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="67ff1-130">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67ff1-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="67ff1-131">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="67ff1-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="67ff1-132">Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67ff1-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ff1-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67ff1-133">See also</span></span>

- [<span data-ttu-id="67ff1-134">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="67ff1-134">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
