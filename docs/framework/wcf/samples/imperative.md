---
title: Imperativ
ms.date: 03/30/2017
ms.assetid: 4f7ce807-c0e4-407a-92a6-22abafb40b51
ms.openlocfilehash: b0a1b1dfca78a844364cfe977860915769980a04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990053"
---
# <a name="imperative"></a><span data-ttu-id="38d6f-102">Imperativ</span><span class="sxs-lookup"><span data-stu-id="38d6f-102">Imperative</span></span>

<span data-ttu-id="38d6f-103">Dieses Beispiel zeigt, wie eine <xref:System.ServiceModel.WSHttpBinding> für einen Dienstcode definiert wird, anstatt die `wsHttpBinding`-Bindung in der Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="38d6f-103">This sample demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span> <span data-ttu-id="38d6f-104">Dieses Beispiel basiert auf der [Einstieg](getting-started-sample.md) , das einen rechnerdienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="38d6f-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>

> [!NOTE]
> <span data-ttu-id="38d6f-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="38d6f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="38d6f-106">Der folgende Code zeigt, wie eine Bindung imperativ im Code definiert wird.</span><span class="sxs-lookup"><span data-stu-id="38d6f-106">The following code demonstrates how to define a binding imperatively in code.</span></span>

```csharp
public static void Main()
{
    WSHttpBinding binding = new WSHttpBinding();
    binding.Name = "binding1";
    binding.HostNameComparisonMode =
        HostNameComparisonMode.StrongWildcard;
    binding.Security.Mode = SecurityMode.Message;
    binding.ReliableSession.Enabled = false;
    binding.TransactionFlow = false;

    Uri baseAddress =
        new Uri("http://localhost:8000/servicemodelsamples/service");

    // Create a ServiceHost for the CalculatorService type and provide the base address.
    using(ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
    {
        serviceHost.AddServiceEndpoint(typeof(ICalculator), 
                                       binding, baseAddress);
        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
        // Close the ServiceHostBase to shutdown the service.
        serviceHost.Close();
    }
}
```

 <span data-ttu-id="38d6f-107">Der Client erstellt einen Kanal, um mit dem Dienst zu kommunizieren, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="38d6f-107">The client creates a channel to communicate with the service as shown in the following sample code.</span></span>

```csharp
WSHttpBinding binding = new WSHttpBinding();
binding.Name = "binding1";
binding.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;
binding.Security.Mode = SecurityMode.Message;
binding.ReliableSession.Enabled = false;
binding.TransactionFlow = false;

String url = "http://localhost:8000/servicemodelsamples/service";
EndpointAddress address = new EndpointAddress(url);
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding,address);
ICalculator channel = channelFactory.CreateChannel();
```

 <span data-ttu-id="38d6f-108">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38d6f-108">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="38d6f-109">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="38d6f-109">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="38d6f-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="38d6f-110">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="38d6f-111">Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="38d6f-111">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="38d6f-112">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="38d6f-112">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="38d6f-113">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="38d6f-113">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38d6f-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="38d6f-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="38d6f-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="38d6f-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="38d6f-116">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="38d6f-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="38d6f-117">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="38d6f-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Imperative`