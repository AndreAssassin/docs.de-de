---
title: Einschränkung
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, throttling sample
- Throttling Sample [Windows Communication Foundation]
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
ms.openlocfilehash: 1611a45efb1cc7bbef524e4a23cc3287b7f51d3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231304"
---
# <a name="throttling"></a><span data-ttu-id="46f51-102">Einschränkung</span><span class="sxs-lookup"><span data-stu-id="46f51-102">Throttling</span></span>
<span data-ttu-id="46f51-103">Im Einschränkungsbeispiel wird die Verwendung von Einschränkungssteuerelementen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="46f51-103">The Throttling sample demonstrates the use of throttling controls.</span></span> <span data-ttu-id="46f51-104">Mit der Einschränkung wird die Anzahl gleichzeitiger Aufrufe, Instanzen oder Sitzungen begrenzt, um eine übermäßige Ressourcenbeanspruchung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="46f51-104">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span> <span data-ttu-id="46f51-105">Das Einschränkungsverhalten wird in Dienstkonfigurations-Dateieinstellungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="46f51-105">Throttling behavior is specified in service configuration file settings.</span></span> <span data-ttu-id="46f51-106">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="46f51-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="46f51-107">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="46f51-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46f51-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="46f51-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="46f51-109">Die Dienstkonfigurationsdatei gibt einschränkungssteuerelemente in einem [ \<ServiceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="46f51-109">The service configuration file specifies throttling controls in a [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="46f51-110">Wie in der Konfiguration angegeben, schränkt der Dienst die maximale Anzahl gleichzeitiger Aufrufe auf 2 und die maximale Anzahl gleichzeitiger Instanzen auf 10 ein.</span><span class="sxs-lookup"><span data-stu-id="46f51-110">As configured, the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span>  
  
 <span data-ttu-id="46f51-111">Zum Vorführen der Einschränkung wird in den Dienstmethoden wie folgt eine Ruhezeit definiert:</span><span class="sxs-lookup"><span data-stu-id="46f51-111">In order to demonstrate throttling we define a sleep time on the service methods as follows:</span></span>  
  
```csharp
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
```  
  
 <span data-ttu-id="46f51-112">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46f51-112">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="46f51-113">Die Add- und Subtract-Methoden werden gleichzeitig ausgeführt, und die Multiply- und Divide-Methoden werden gleichzeitig ausgeführt, um zu beweisen, dass höchstens 2 Methoden gleichzeitig ausgeführt werden können, was die Einschränkung dann veranschaulichen würde.</span><span class="sxs-lookup"><span data-stu-id="46f51-113">The Add and Subtract methods are executed concurrently and the Multiply and Divide methods are executed concurrently proving that not more than 2 methods can be executed concurrently thus demonstrating throttling.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="46f51-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="46f51-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="46f51-115">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="46f51-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="46f51-116">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="46f51-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="46f51-117">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="46f51-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46f51-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="46f51-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="46f51-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="46f51-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="46f51-120">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="46f51-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="46f51-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="46f51-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
