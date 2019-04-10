---
title: Kanalfactory
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: 0bcaa739a51d168e18c809804b7da6948ab61e9d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315529"
---
# <a name="channel-factory"></a><span data-ttu-id="e43b2-102">Kanalfactory</span><span class="sxs-lookup"><span data-stu-id="e43b2-102">Channel Factory</span></span>
<span data-ttu-id="e43b2-103">In diesem Beispiel wird veranschaulicht, wie eine Clientanwendung einen Kanal mit der <xref:System.ServiceModel.ChannelFactory>-Klasse und nicht mit einem generierten Client erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e43b2-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="e43b2-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="e43b2-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e43b2-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e43b2-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e43b2-106">In diesem Beispiel wird mithilfe der <xref:System.ServiceModel.ChannelFactory%601>-Klasse ein Kanal für einen Dienstendpunkt erstellt.</span><span class="sxs-lookup"><span data-stu-id="e43b2-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="e43b2-107">Normalerweise generieren Sie zum Erstellen eines Kanals zu einem Dienstendpunkt einen Clienttyp mit dem [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) und erstellen Sie eine Instanz des generierten Typs.</span><span class="sxs-lookup"><span data-stu-id="e43b2-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="e43b2-108">Sie können einen Kanal auch mithilfe der <xref:System.ServiceModel.ChannelFactory%601>-Klasse erstellen, wie in diesem Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e43b2-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="e43b2-109">Im folgenden Beispielcode erstellte Dienst ist identisch mit dem Dienst in der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e43b2-109">The service created by the following sample code is identical to the service in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
```csharp  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e43b2-110">Wenn Sie dieses Beispiel in einem Szenario computerübergreifend ausführen, müssen Sie "localhost" im oben stehenden Code durch den vollqualifizierten Namen des Computers ersetzen, auf dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e43b2-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="e43b2-111">Im Beispiel wird die Endpunktadresse nicht in der Konfiguration festgelegt, daher muss dies im Code erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e43b2-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>  
  
 <span data-ttu-id="e43b2-112">Nach dem Erstellen des Kanals können Dienstvorgänge wie bei einem generierten Client aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e43b2-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>  
  
```csharp  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
 <span data-ttu-id="e43b2-113">Zum Schließen des Kanals muss dieser zunächst in eine <xref:System.ServiceModel.IClientChannel>-Schnittstelle umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e43b2-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="e43b2-114">Dies ist erforderlich, da der Kanal wie generiert in der Clientanwendung mit der `ICalculator`-Schnittstelle deklariert wird. Diese verfügt über Methoden wie `Add` und `Subtract`, nicht jedoch über `Close`.</span><span class="sxs-lookup"><span data-stu-id="e43b2-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="e43b2-115">Die `Close`-Methode stammt aus der <xref:System.ServiceModel.ICommunicationObject>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e43b2-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>  
  
```csharp  
// Close the channel.  
 ((IClientChannel)client).Close();  
```  
  
 <span data-ttu-id="e43b2-116">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e43b2-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e43b2-117">Drücken Sie im Clientfenster die EINGABETASTE, um die Clientanwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e43b2-117">Press ENTER in the client window to shut down the client application.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e43b2-118">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e43b2-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e43b2-119">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e43b2-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e43b2-120">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e43b2-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="e43b2-121">Beachten Sie, dass das Veröffentlichen von Metadaten in diesem Beispiel nicht aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e43b2-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="e43b2-122">Sie müssen zuerst das Veröffentlichen von Metadaten aktivieren, damit der Clienttyp in diesem Beispiel erneut generiert wird.</span><span class="sxs-lookup"><span data-stu-id="e43b2-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>  
  
3. <span data-ttu-id="e43b2-123">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e43b2-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="e43b2-124">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="e43b2-124">To run the sample cross machine</span></span>  
  
1. <span data-ttu-id="e43b2-125">Ersetzen Sie "localhost" im folgenden Code durch den vollqualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e43b2-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>  
  
    ```csharp  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e43b2-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e43b2-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e43b2-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e43b2-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e43b2-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e43b2-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e43b2-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e43b2-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
