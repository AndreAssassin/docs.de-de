---
title: ConcurrencyMode Reentrant
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 2170b029f1cb4a85a1b2688fc1143ffcd1682fe6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299819"
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="19cc5-102">ConcurrencyMode Reentrant</span><span class="sxs-lookup"><span data-stu-id="19cc5-102">ConcurrencyMode Reentrant</span></span>
<span data-ttu-id="19cc5-103">In diesem Beispiel werden die Notwendigkeit und Auswirkungen der Verwendung von ConcurrencyMode.Reentrant in einer Dienstimplementierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="19cc5-103">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="19cc5-104">ConcurrencyMode.Reentrant impliziert, dass der Dienst (oder Rückruf) nur jeweils eine Nachricht verarbeitet (analog zu `ConcurencyMode.Single`).</span><span class="sxs-lookup"><span data-stu-id="19cc5-104">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="19cc5-105">Um Threadsicherheit zu gewährleisten, Windows Communication Foundation (WCF) sperrt die `InstanceContext` eine Nachricht verarbeitet, sodass keine weiteren Nachrichten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="19cc5-105">To ensure thread safety, Windows Communication Foundation (WCF) locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="19cc5-106">Im Reentrant-Modus wird der `InstanceContext` entsperrt, kurz bevor der Dienst einen ausgehenden Aufruf ausführt. So kann der folgende Aufruf (der wie in diesem Beispiel dargestellt wiedereintrittsfähig sein kann) beim nächsten Mal gesperrt werden, wenn er den Dienst erreicht.</span><span class="sxs-lookup"><span data-stu-id="19cc5-106">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="19cc5-107">Zum Veranschaulichen des Verhaltens wird im Beispiel gezeigt, wie ein Client und ein Dienst untereinander Nachrichten mit einem Duplexvertrag senden können.</span><span class="sxs-lookup"><span data-stu-id="19cc5-107">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="19cc5-108">Bei dem definierten Vertrag handelt es sich um einen Duplexvertrag, bei dem die `Ping`-Methode vom Dienst und die Rückrufmethode `Pong` vom Client implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="19cc5-108">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="19cc5-109">Ein Client ruft die `Ping`-Methode des Servers mit einer Tickanzahl auf und initiiert so den Aufruf.</span><span class="sxs-lookup"><span data-stu-id="19cc5-109">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="19cc5-110">Der Dienst überprüft, ob die Anzahl der Ticks ungleich 0 (null) ist, und ruft dann die `Pong`-Methode des Rückrufs auf, während die Tickanzahl verringert wird.</span><span class="sxs-lookup"><span data-stu-id="19cc5-110">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="19cc5-111">Dies wird im Beispiel mit dem folgenden Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="19cc5-111">This is done by the following code in the sample.</span></span>  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 Die `Pong`-Implementierung des Rückrufs weist die gleiche Logik wie die `Ping`-Implementierung auf. Das heißt, es wird überprüft, ob die Anzahl der Ticks ungleich 0 (null) ist, und dann wird die `Ping`-Methode über den Rückrufkanal aufgerufen, wobei die Anzahl der Ticks um 1 reduziert wird. (in diesem Fall ist der Rückrufkanal der Kanal, über den die ursprüngliche `Ping`-Meldung gesendet wurde.) Wenn die Anzahl der Ticks 0 erreicht, kehrt die Methode zurück und entpackt dabei alle Antworten auf den ersten Aufruf, der vom Client getätigt wurde, der den Aufruf initiiert hat. <span data-ttu-id="19cc5-115">Dies wird in der Rückrufimplementierung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="19cc5-115">This is shown in the callback implementation.</span></span>  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 Die `Ping`-Methode und die `Pong`-Methode sind Anforderung/Antwort-Methoden. Der erste Aufruf von `Ping` wird daher erst zurückgegeben, wenn der Aufruf von `CallbackChannel<T>.Pong()` zurückgegeben wurde. Auf dem Client kann die `Pong`-Methode erst zurückgegeben werden, wenn der nächste `Ping`-Aufruf, den sie vorgenommen hat, zurückgegeben wurde. <span data-ttu-id="19cc5-118">Da der Rückruf und der Dienst ausgehende Anforderung/Antwort-Aufrufe ausführen müssen, damit sie für die ausstehende Anforderung antworten können, müssen beide Implementierungen mit dem ConcurrencyMode.Reentrant-Verhalten gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="19cc5-118">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="19cc5-119">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="19cc5-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="19cc5-120">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="19cc5-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="19cc5-121">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="19cc5-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="19cc5-122">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="19cc5-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="19cc5-123">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="19cc5-123">Demonstrates</span></span>  
 <span data-ttu-id="19cc5-124">Erstellen Sie zum Ausführen des Beispiels das Client- und Serverprojekt.</span><span class="sxs-lookup"><span data-stu-id="19cc5-124">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="19cc5-125">Klicken Sie dann zwei Befehlsfenster öffnen, und wechseln Sie in der \<Beispiel > \CS\Service\bin\debug und \<Beispiel > \CS\Client\bin\debug Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="19cc5-125">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="19cc5-126">Starten Sie den Dienst durch Eingabe `service.exe` und rufen Sie dann die Client.exe mit der Anfangswert von Ticks, die als Eingabeargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="19cc5-126">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="19cc5-127">Es wird eine Beispielausgabe für 10 Ticks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="19cc5-127">A sample output for 10 ticks is shown.</span></span>  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="19cc5-128">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="19cc5-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="19cc5-129">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="19cc5-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="19cc5-130">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="19cc5-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19cc5-131">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="19cc5-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
