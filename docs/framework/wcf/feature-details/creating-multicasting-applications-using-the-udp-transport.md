---
title: Erstellen von Multicastanwendungen mithilfe des UDP-Transports
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: b65a277b6e76767d1e3bfdbebbac5051759986e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857193"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="37f77-102">Erstellen von Multicastanwendungen mithilfe des UDP-Transports</span><span class="sxs-lookup"><span data-stu-id="37f77-102">Creating Multicasting Applications using the UDP Transport</span></span>
<span data-ttu-id="37f77-103">Multicastanwendungen senden kleine Nachrichten gleichzeitig an eine große Anzahl von Empfängern, ohne dass eine Punkt-zu-Punkt-Verbindung eingerichtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="37f77-103">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="37f77-104">Bei diesen Anwendungen hat Geschwindigkeit Vorrang vor Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="37f77-104">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="37f77-105">Das heißt, es ist wichtiger, Daten zeitgerecht zu senden, als sicherzustellen, dass eine Nachricht auch tatsächlich empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="37f77-105">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="37f77-106">WCF unterstützt jetzt mit der <xref:System.ServiceModel.UdpBinding> das Schreiben von Multicastanwendungen.</span><span class="sxs-lookup"><span data-stu-id="37f77-106">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="37f77-107">Dieser Transport ist in Szenarien nützlich, in denen ein Dienst kleine Nachrichten an eine große Anzahl von Clients gleichzeitig senden muss.</span><span class="sxs-lookup"><span data-stu-id="37f77-107">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="37f77-108">Eine Börsenticker-Anwendung ist ein Beispiel für einen solchen Dienst.</span><span class="sxs-lookup"><span data-stu-id="37f77-108">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="37f77-109">Implementieren einer Multicastanwendung</span><span class="sxs-lookup"><span data-stu-id="37f77-109">Implementing a Multicast Application</span></span>  
 <span data-ttu-id="37f77-110">Um eine Multicastanwendung zu implementieren, definieren Sie einen Dienstvertrag und implementieren diesen für jede Softwarekomponente, die auf die Multicastnachrichten antworten muss.</span><span class="sxs-lookup"><span data-stu-id="37f77-110">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="37f77-111">Zum Beispiel kann eine Börsenticker-Anwendung einen Dienstvertrag definieren:</span><span class="sxs-lookup"><span data-stu-id="37f77-111">For example, a stock ticker application might define a service contract:</span></span>  
  
```csharp
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 <span data-ttu-id="37f77-112">Jede Anwendung, die Multicastnachrichten empfangen möchte, muss einen Dienst hosten, der diese Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="37f77-112">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="37f77-113">Das folgende Codebeispiel veranschaulicht, wie Multicastnachrichten empfangen werden:</span><span class="sxs-lookup"><span data-stu-id="37f77-113">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
```csharp
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 <span data-ttu-id="37f77-114">Die Anwendung gibt die UDP-Adresse an, an der alle Dienste lauschen.</span><span class="sxs-lookup"><span data-stu-id="37f77-114">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="37f77-115">Ein neuer <xref:System.ServiceModel.ServiceHost> wird erstellt, und mit der <xref:System.ServiceModel.UdpBinding> wird ein Dienstendpunkt verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="37f77-115">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="37f77-116">Anschließend wird der <xref:System.ServiceModel.ServiceHost> geöffnet, und dieser beginnt mit dem Lauschen auf eingehende Meldungen.</span><span class="sxs-lookup"><span data-stu-id="37f77-116">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="37f77-117">In diesem Szenariotyp werden Multicastnachrichten tatsächlich vom Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="37f77-117">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="37f77-118">Jeder Dienst, der an der richtigen UDP-Adresse lauscht, empfängt die Multicastnachrichten.</span><span class="sxs-lookup"><span data-stu-id="37f77-118">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="37f77-119">Im Folgenden finden Sie ein Beispiel für einen Client, der Multicastnachrichten sendet:</span><span class="sxs-lookup"><span data-stu-id="37f77-119">Here is an example of a client that sends out multicast messages:</span></span>  
  
```csharp
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory 
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine($"sent stock info at {DateTime.Now}");
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 <span data-ttu-id="37f77-120">Dieser Code generiert Börseninformationen und verwendet dann den Dienstvertrag IStockTicker, um Multicastnachrichten an Aufrufdienste zu senden, die an der richtigen UDP-Adresse lauschen.</span><span class="sxs-lookup"><span data-stu-id="37f77-120">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="37f77-121">UDP und zuverlässiges Messaging</span><span class="sxs-lookup"><span data-stu-id="37f77-121">UDP and Reliable Messaging</span></span>  
 <span data-ttu-id="37f77-122">Da es sich bei UDP um ein einfaches Protokoll handelt, unterstützt die UDP-Bindung kein zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="37f77-122">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="37f77-123">Wenn Sie sicherstellen müssen, dass Nachrichten von einem Remoteendpunkt empfangen werden, verwenden Sie einen Transport, der zuverlässiges Messaging unterstützt, z. B. HTTP oder TCP.</span><span class="sxs-lookup"><span data-stu-id="37f77-123">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="37f77-124">Weitere Informationen zu reliable messaging finden Sie unter https://go.microsoft.com/fwlink/?LinkId=231830</span><span class="sxs-lookup"><span data-stu-id="37f77-124">For more information about reliable messaging see https://go.microsoft.com/fwlink/?LinkId=231830</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="37f77-125">Bidirektionales Multicastmessaging</span><span class="sxs-lookup"><span data-stu-id="37f77-125">Two-way Multicast Messaging</span></span>  
 <span data-ttu-id="37f77-126">Während Multicastnachrichten im Allgemeinen unidirektional sind, unterstützt UdpBinding den Austausch von Anforderungs-/Antwortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="37f77-126">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="37f77-127">Die mithilfe des UDP-Transports gesendeten Nachrichten enthalten eine Absender- und eine Empfängeradresse.</span><span class="sxs-lookup"><span data-stu-id="37f77-127">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="37f77-128">Besondere Sorgfalt erfordert die Absenderadresse, da sie während der Übertragung möglicherweise böswillig geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="37f77-128">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="37f77-129">Die Adresse kann mithilfe des folgenden Codes überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="37f77-129">The address can be checked using the following code:</span></span>  
  
```csharp
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 <span data-ttu-id="37f77-130">Der Code überprüft das erste Byte der Absenderadresse, um zu ermitteln, ob sie 0xE0 enthält, was bedeutet, dass es sich um eine Multicastadresse handelt.</span><span class="sxs-lookup"><span data-stu-id="37f77-130">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="37f77-131">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="37f77-131">Security Considerations</span></span>  
 <span data-ttu-id="37f77-132">Beim Lauschen auf Multicastnachrichten wird ein ICMP-Paket an den Router gesendet, um ihn davon in Kenntnis setzen, ob an der Multicastadresse gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="37f77-132">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="37f77-133">Jeder Benutzer im lokalen Subnetz mit entsprechender Berechtigung kann auf diese Pakettypen lauschen und ermitteln, an welcher Multicastadresse und welchem Port gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="37f77-133">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="37f77-134">Aus Sicherheitsgründen sollte die IP-Adresse des Absenders nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37f77-134">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="37f77-135">Diese Information kann gespooft sein, sodass eine Anwendung Antworten an den falschen Computer sendet.</span><span class="sxs-lookup"><span data-stu-id="37f77-135">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="37f77-136">Eine Möglichkeit, dieses Risiko abzuschwächen, ist das Aktivieren der Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="37f77-136">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="37f77-137">Auf Netzwerkebene kann auch Internetprotokollsicherheit (Internet Protocol Security, IPSec) und/oder Netzwerkzugriffsschutz (Network Access Protection, NAP) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37f77-137">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
