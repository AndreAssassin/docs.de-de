---
title: Sicherheitsvalidierung
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: b6e97b7b8662a13628bd8b0b353e4d28c0c84a9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202871"
---
# <a name="security-validation"></a><span data-ttu-id="183c9-102">Sicherheitsvalidierung</span><span class="sxs-lookup"><span data-stu-id="183c9-102">Security Validation</span></span>
<span data-ttu-id="183c9-103">Dieses Beispiel veranschaulicht die Verwendung eines benutzerdefinierten Verhaltens, mit dem Dienste auf einem Computer überprüft werden, um sicherzustellen, dass sie bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="183c9-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="183c9-104">In diesem Beispiel werden Dienste vom benutzerdefinierten Verhalten überprüft, indem jeder Endpunkt im Dienst gescannt und dahingehend überprüft wird, ob er sichere Bindungselemente enthält.</span><span class="sxs-lookup"><span data-stu-id="183c9-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="183c9-105">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="183c9-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="183c9-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="183c9-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="183c9-107">Benutzerdefiniertes Verhalten zur Endpunktvalidierung</span><span class="sxs-lookup"><span data-stu-id="183c9-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="183c9-108">Durch Hinzufügen von Benutzercode zur `Validate`-Methode aus der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle kann einem Dienst oder einem Endpunkt benutzerdefiniertes Verhalten zugewiesen werden, um benutzerdefinierte Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="183c9-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="183c9-109">Mit dem folgenden Code wird jeder in einem Dienst enthaltene Endpunkt durchlaufen und deren Bindungsauflistungen nach sicheren Bindungen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="183c9-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```csharp
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their    
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="183c9-110">Durch Hinzufügen des folgenden Codes zu der Datei "Web.config" wird die `serviceValidate`-Verhaltenserweiterung für den zu erkennenden Dienst hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="183c9-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 <span data-ttu-id="183c9-111">Nach dem Hinzufügen der Verhaltenserweiterung zum Dienst kann nun das `endpointValidate`-Verhalten zur Liste der Verhaltensweisen in der Datei "Web.config" (und damit zum Dienst) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="183c9-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="183c9-112">Wenn Verhalten und deren Erweiterungen der Datei Web.config hinzugefügt werden, wird das Verhalten auf einzelne Dienste angewendet. Werden Sie aber der Datei Machine.config hinzugefügt, gilt das Verhalten für alle aktiven Dienste auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="183c9-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="183c9-113">Beim Hinzufügen von Verhalten zu allen Diensten wird empfohlen, vorher die Datei Machine.config zu sichern.</span><span class="sxs-lookup"><span data-stu-id="183c9-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="183c9-114">Führen Sie nun den Client aus dem Verzeichnis client\bin dieses Beispiels aus.</span><span class="sxs-lookup"><span data-stu-id="183c9-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="183c9-115">Eine Ausnahme tritt auf, mit der folgenden Meldung: "Der angeforderte Dienst"http://localhost/servicemodelsamples/service.svc' konnte nicht aktiviert werden. "</span><span class="sxs-lookup"><span data-stu-id="183c9-115">An exception has occurs with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="183c9-116">Dies ist zu erwarten, da das Endpunktvalidierungsverhalten einen Endpunkt als unsicher betrachtet und verhindert, dass der Dienst startet.</span><span class="sxs-lookup"><span data-stu-id="183c9-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="183c9-117">Außerdem löst das Verhalten eine interne Ausnahme aus, die beschreibt, welcher Endpunkt unsicher ist, und schreibt eine Nachricht für die Ereignisanzeige unter der Quelle "System.ServiceModel 4.0.0.0" und der Kategorie "WebHost".</span><span class="sxs-lookup"><span data-stu-id="183c9-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="183c9-118">Es ist auch möglich, für den Dienst aus diesem Beispiel die Ablaufverfolgung einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="183c9-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="183c9-119">Dadurch wird dem Benutzer ermöglicht, die vom Endpunktvalidierungsverhalten ausgelösten Ausnahmen anzuzeigen, indem er die resultierenden Dienstablaufverfolgungen mit dem Service Trace Viewer öffnet.</span><span class="sxs-lookup"><span data-stu-id="183c9-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="183c9-120">So zeigen Sie Ausnahmemeldungen von fehlgeschlagenen Endpunktvalidierungen in der Ereignisanzeige an</span><span class="sxs-lookup"><span data-stu-id="183c9-120">To view failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1.  <span data-ttu-id="183c9-121">Klicken Sie auf die **starten** Menü **ausführen...** .</span><span class="sxs-lookup"><span data-stu-id="183c9-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2.  <span data-ttu-id="183c9-122">Typ `eventvwr` , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="183c9-122">Type `eventvwr` and click **OK**.</span></span>  
  
3.  <span data-ttu-id="183c9-123">Klicken Sie im Fenster-Ereignisanzeige auf **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="183c9-123">In the Event Viewer window, click **Application**.</span></span>  
  
4.  <span data-ttu-id="183c9-124">Doppelklicken Sie auf das Ereignis "System.ServiceModel 4.0.0.0" zuletzt hinzugefügte unter der Kategorie "WebHost" in der **Anwendung** Fenster aus, um Nachrichten von unsicheren Endpunkten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="183c9-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="183c9-125">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="183c9-125">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="183c9-126">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="183c9-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="183c9-127">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="183c9-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="183c9-128">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="183c9-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="183c9-129">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="183c9-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="183c9-130">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="183c9-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="183c9-131">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="183c9-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="183c9-132">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="183c9-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="183c9-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="183c9-133">See also</span></span>

- [<span data-ttu-id="183c9-134">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="183c9-134">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
