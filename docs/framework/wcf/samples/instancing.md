---
title: Instanziierung
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
ms.openlocfilehash: 2cc3c54563b261d49264314f7306193accbe4040
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311434"
---
# <a name="instancing"></a><span data-ttu-id="6c1e9-102">Instanziierung</span><span class="sxs-lookup"><span data-stu-id="6c1e9-102">Instancing</span></span>
<span data-ttu-id="6c1e9-103">Im Beispiel zur Instanziierung wird die Einstellung zum Instanziierungsverhalten veranschaulicht, die steuert, wie Instanzen einer Dienstklasse als Reaktion auf Clientanforderungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-103">The Instancing sample demonstrates the instancing behavior setting, which controls how instances of a service class are created in response to client requests.</span></span> <span data-ttu-id="6c1e9-104">Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="6c1e9-105">In diesem Beispiel wird ein neuer Vertrag (`ICalculatorInstance`) definiert, der von `ICalculator` erbt.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-105">This sample defines a new contract, `ICalculatorInstance`, which inherits from `ICalculator`.</span></span> <span data-ttu-id="6c1e9-106">Der von `ICalculatorInstance` angegebene Vertrag stellt drei zusätzliche Vorgänge zum Überprüfen des Zustands der Dienstinstanz bereit.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-106">The contract specified by `ICalculatorInstance` provides three additional operations for inspecting the state of the service instance.</span></span> <span data-ttu-id="6c1e9-107">Indem Sie die Einstellung für die Instanziierung ändern, können Sie Änderungen im Verhalten beobachten, wenn Sie den Client ausführen.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-107">By altering the instancing setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="6c1e9-108">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c1e9-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6c1e9-110">Es stehen die folgenden Instanziierungsmodi zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6c1e9-110">The following instancing modes are available:</span></span>  
  
-   <span data-ttu-id="6c1e9-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: Eine neue Dienstinstanz wird für jede Clientanforderung erstellt.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-111"><xref:System.ServiceModel.InstanceContextMode.PerCall>: A new service instance is created for each client request.</span></span>  
  
-   <span data-ttu-id="6c1e9-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: Eine neue Instanz wird für jede neue Clientsitzung erstellt und verwaltet werden, für die Lebensdauer der Sitzung (erfordert eine Bindung, die Sitzung unterstützt).</span><span class="sxs-lookup"><span data-stu-id="6c1e9-112"><xref:System.ServiceModel.InstanceContextMode.PerSession>: A new instance is created for each new client session, and maintained for the lifetime of that session (requires a binding that supports session).</span></span>  
  
-   <span data-ttu-id="6c1e9-113"><xref:System.ServiceModel.InstanceContextMode.Single>: Eine einzelne Instanz der Dienstklasse verarbeitet alle Clientanforderungen für die Lebensdauer der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-113"><xref:System.ServiceModel.InstanceContextMode.Single>: A single instance of the service class handles all client requests for the lifetime of the application.</span></span>  
  
 <span data-ttu-id="6c1e9-114">Die Dienstklasse gibt das Instanziierungsverhalten mit dem `[ServiceBehavior(InstanceContextMode=<setting>)]`-Attribut an, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-114">The service class specifies instancing behavior with the `[ServiceBehavior(InstanceContextMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="6c1e9-115">Indem Sie unterschiedliche Zeilen auskommentieren, können Sie das Verhalten der einzelnen Instanzmodi beobachten.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-115">By changing which lines are commented out, you can observe the behavior of each of the instance modes.</span></span> <span data-ttu-id="6c1e9-116">Denken Sie daran, den Dienst nach dem Ändern des Instanziierungsmodus neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-116">Remember to rebuild the service after changing the instancing mode.</span></span> <span data-ttu-id="6c1e9-117">Es gibt keine Einstellungen in Bezug auf die Instanziierung, die auf dem Client angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-117">There are no instancing-related settings to specify on the client.</span></span>  
  
```csharp
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed   
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="6c1e9-118">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6c1e9-119">Es wird der Instanzmodus angezeigt, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-119">The instance mode the service is running under is displayed.</span></span> <span data-ttu-id="6c1e9-120">Nach jedem Vorgang werden die Instanz-ID und die Vorgangsanzahl angezeigt, um das Verhalten des Instanziierungsmodus darzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-120">After each operation, the instance ID and operation count are displayed to reflect the behavior of the instancing mode.</span></span> <span data-ttu-id="6c1e9-121">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-121">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6c1e9-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6c1e9-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6c1e9-123">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6c1e9-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6c1e9-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6c1e9-125">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6c1e9-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c1e9-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c1e9-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6c1e9-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c1e9-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6c1e9-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
