---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 92a0bac3cf6ac6b57792419c913ec481ff0ee6c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769449"
---
# <a name="srmp"></a><span data-ttu-id="01367-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="01367-102">SRMP</span></span>
<span data-ttu-id="01367-103">In diesem Beispiel wird veranschaulicht, wie eine abgewickelte Warteschlangenkommunikation mithilfe von Message Queuing (MSMQ) über HTTP durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01367-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="01367-104">In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="01367-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="01367-105">Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet.</span><span class="sxs-lookup"><span data-stu-id="01367-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="01367-106">Der Dienst empfängt Nachrichten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="01367-106">The service receives messages from the queue.</span></span> <span data-ttu-id="01367-107">Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="01367-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="01367-108">MSMQ aktiviert die Verwendung des HTTP (einschließlich der Verwendung des HTTPS), um Nachrichten an eine Warteschlange zu senden.</span><span class="sxs-lookup"><span data-stu-id="01367-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="01367-109">In diesem Beispiel zeigen wir Ihnen, dass mit Windows Communication Foundation (WCF) Kommunikation und Senden von Nachrichten über HTTP in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="01367-109">In this example, we demonstrate using Windows Communication Foundation (WCF) queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="01367-110">MSMQ verwendet ein Protokoll namens SRMP, das ein SOAP-basiertes Protokoll für Kommunikation über HTTP ist.</span><span class="sxs-lookup"><span data-stu-id="01367-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="01367-111">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="01367-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="01367-112">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="01367-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="01367-113">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="01367-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="01367-114">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="01367-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="01367-115">Vor dem Ausführen des Beispiels in **Windows-Komponenten hinzufügen/entfernen**, stellen Sie sicher, dass MSMQ installiert ist mit HTTP-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="01367-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="01367-116">Die Installation der HTTP-Unterstützung installiert automatisch Internetinformationsdienste (IIS) und fügt die Protokollunterstützung in IIS für MSMQ hinzu.</span><span class="sxs-lookup"><span data-stu-id="01367-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5. <span data-ttu-id="01367-117">Wenn Sie sichergehen möchten, dass HTTP für die Kommunikation verwendet wird, können Sie MSMQ aktivieren, um eine Ausführung im geschützten Modus zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="01367-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="01367-118">Hierdurch wird sichergestellt, dass keine Nachrichten an Warteschlangen, die auf dem Computer gehostet werden, durch Nicht-HTTP-Transporte empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="01367-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6. <span data-ttu-id="01367-119">Nachdem Sie MSMQ ausgewählt haben, um im geschützten Modus auszuführen, erfordert der Computer auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] einen Neustart.</span><span class="sxs-lookup"><span data-stu-id="01367-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
7. <span data-ttu-id="01367-120">Führen Sie den Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="01367-120">Run the service.</span></span>  
  
8. <span data-ttu-id="01367-121">Führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="01367-121">Run the client.</span></span> <span data-ttu-id="01367-122">Ändern Sie die Endpunktadresse so, dass diese auf den Computernamen oder die IP-Adresse anstelle von "localhost" verweist.</span><span class="sxs-lookup"><span data-stu-id="01367-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="01367-123">Der Client sendet eine Nachricht und wird beendet.</span><span class="sxs-lookup"><span data-stu-id="01367-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01367-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01367-124">Requirements</span></span>  
 <span data-ttu-id="01367-125">Zum Ausführen dieses Beispiels muss IIS zusätzlich zu MSMQ sowohl auf dem Dienst- als auch auf dem Clientcomputer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="01367-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="01367-126">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="01367-126">Demonstrates</span></span>  
 <span data-ttu-id="01367-127">Das Beispiel veranschaulicht das Senden von WCF mit MSMQ über HTTP Nachrichten in der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="01367-127">The sample demonstrates sending WCF queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="01367-128">Dies wird auch als SRMP-Messaging bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="01367-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="01367-129">Wenn eine in der Warteschlange befindliche Nachricht gesendet wird, überträgt MSMQ auf dem sendenden Computer die Nachrichten über TCP- oder HTTP-Transport an den empfangenden Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="01367-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="01367-130">Indem er SRMP auswählt, gibt der Benutzer die Auswahl von HTTP als Transport für Warteschlangenübertragung an.</span><span class="sxs-lookup"><span data-stu-id="01367-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="01367-131">SRMP Secure aktiviert die Verwendung von HTTPS.</span><span class="sxs-lookup"><span data-stu-id="01367-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01367-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01367-132">Example</span></span>  
 <span data-ttu-id="01367-133">Der Beispielcode basiert auf dem durchgeführten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="01367-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="01367-134">Wie über SRMP eine Nachricht zu einer Warteschlange gesendet und wie eine Nachricht aus einer Warteschlange empfangen wird, entspricht dem Senden und Empfangen von Nachrichten mithilfe eines systemeigenen Protokolls.</span><span class="sxs-lookup"><span data-stu-id="01367-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="01367-135">Die Konfiguration für den Client wird geändert, um die Auswahl des Warteschlangen-Übertragungsprotokolls anzugeben.</span><span class="sxs-lookup"><span data-stu-id="01367-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="01367-136">Das Warteschlangen-Übertragungsprotokoll kann systemeigen, SRMP oder SrmpSecure sein.</span><span class="sxs-lookup"><span data-stu-id="01367-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="01367-137">Standardmäßig ist das Übertragungsprotokoll systemeigen.</span><span class="sxs-lookup"><span data-stu-id="01367-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="01367-138">Der Client und der Dienst legen in diesem Beispiel in der Konfiguration die Verwendung von SRMP fest.</span><span class="sxs-lookup"><span data-stu-id="01367-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="01367-139">Bei SRMP gibt es Einschränkungen in Bezug auf die Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="01367-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="01367-140">Die Standard-MSMQ-Transportsicherheit erfordert Active Directory. Daher müssen sich der sendende und der empfangende Warteschlangen-Manager auf der gleichen Windows-Domäne befinden.</span><span class="sxs-lookup"><span data-stu-id="01367-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="01367-141">Dies ist beim Senden von Nachrichten über die HTTP-Grenze nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="01367-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="01367-142">Auf diese Weise funktioniert die Standardtransportsicherheit nicht.</span><span class="sxs-lookup"><span data-stu-id="01367-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="01367-143">Die Transportsicherheit muss auf Zertifikat (Certificate) festgelegt werden, wenn Transportsicherheit gewünscht wird.</span><span class="sxs-lookup"><span data-stu-id="01367-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="01367-144">Nachrichtensicherheit kann auch genutzt werden, um die Nachricht zu schützen.</span><span class="sxs-lookup"><span data-stu-id="01367-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="01367-145">In diesem Beispiel werden sowohl Transport- als auch Nachrichtensicherheit ausgeschaltet, um SRMP-Messaging zu illustrieren.</span><span class="sxs-lookup"><span data-stu-id="01367-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="01367-146">Die Durchführung des Beispiels führt zu folgender Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="01367-146">Running the sample yields the following output.</span></span>  
  
```  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="01367-147">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="01367-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="01367-148">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="01367-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01367-149">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="01367-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01367-150">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="01367-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
