---
title: Migrieren von .NET-Remoting zu WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 4ca96fe38d766ffe48ab17dc113f4fce8997a0a8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651087"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="fb7cc-102">Migrieren von .NET-Remoting zu WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-102">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="fb7cc-103">Dieser Artikel beschreibt die Vorgehensweise zum Migrieren einer Anwendung, die .NET Remoting zur Verwendung von Windows Communication Foundation (WCF) nutzt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-103">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="fb7cc-104">Es werden ähnliche Konzepte dieser zwei Produkte verglichen, und es wird beschrieben, wie verschiedene Remoting-Szenarien in WCF realisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-104">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="fb7cc-105">.NET Remoting ist ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-105">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="fb7cc-106">Seine Verwendung in Umgebungen mit gemischten Vertrauensstellungen ist nicht sicher, da keine getrennten Vertrauensebenen zwischen Client und Server eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-106">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="fb7cc-107">Beispielsweise sollten Sie nie einen .NET Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-107">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="fb7cc-108">Es wird empfohlen, vorhandene Remoting-Anwendungen auf neuere und sicherere Technologien zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-108">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="fb7cc-109">Wenn das Anwendungsdesign nur HTTP und RESTful verwendet, wird die ASP.NET-Web-API empfohlen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-109">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="fb7cc-110">Weitere Informationen finden Sie unter "ASP.NET-Web-API".</span><span class="sxs-lookup"><span data-stu-id="fb7cc-110">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="fb7cc-111">Wenn die Anwendung auf SOAP basiert oder Nicht-HTTP-Protokolle wie z. B. TCP erfordert, empfehlen wir WCF.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-111">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="fb7cc-112">Vergleich von .NET Remoting und WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-112">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="fb7cc-113">In diesem Abschnitt werden die grundlegenden Bausteine von .NET Remoting mit ihren Entsprechungen in WCF verglichen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-113">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="fb7cc-114">Diese Bausteine werden später verwendet, um einige gängige Client/Server-Szenarien in WCF zu erstellen. Das folgende Diagramm zeigt die wichtigsten Ähnlichkeiten und Unterschiede zwischen .NET Remoting und WCF.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-114">We will use these building blocks later to create some common client-server scenarios in WCF.The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="fb7cc-115">.NET-Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="fb7cc-115">.NET Remoting</span></span>|<span data-ttu-id="fb7cc-116">WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-116">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="fb7cc-117">Servertyp</span><span class="sxs-lookup"><span data-stu-id="fb7cc-117">Server type</span></span>|<span data-ttu-id="fb7cc-118">MarshalByRefObject-Unterklasse</span><span class="sxs-lookup"><span data-stu-id="fb7cc-118">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="fb7cc-119">Markierung mit [ServiceContract]-Attribut</span><span class="sxs-lookup"><span data-stu-id="fb7cc-119">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="fb7cc-120">Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="fb7cc-120">Service operations</span></span>|<span data-ttu-id="fb7cc-121">Öffentliche Methoden für Servertyp</span><span class="sxs-lookup"><span data-stu-id="fb7cc-121">Public methods on server type</span></span>|<span data-ttu-id="fb7cc-122">Markierung mit [OperationContract]-Attribut</span><span class="sxs-lookup"><span data-stu-id="fb7cc-122">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="fb7cc-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="fb7cc-123">Serialization</span></span>|<span data-ttu-id="fb7cc-124">ISerializable oder [Serializable]</span><span class="sxs-lookup"><span data-stu-id="fb7cc-124">ISerializable or [Serializable]</span></span>|<span data-ttu-id="fb7cc-125">DataContractSerializer oder XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="fb7cc-125">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="fb7cc-126">Übergebene Objekte</span><span class="sxs-lookup"><span data-stu-id="fb7cc-126">Objects passed</span></span>|<span data-ttu-id="fb7cc-127">Als Wert oder Verweis</span><span class="sxs-lookup"><span data-stu-id="fb7cc-127">By-value or by-reference</span></span>|<span data-ttu-id="fb7cc-128">Nur als Wert</span><span class="sxs-lookup"><span data-stu-id="fb7cc-128">By-value only</span></span>|  
|<span data-ttu-id="fb7cc-129">Fehler/Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fb7cc-129">Errors/exceptions</span></span>|<span data-ttu-id="fb7cc-130">Jede serialisierbare Ausnahme</span><span class="sxs-lookup"><span data-stu-id="fb7cc-130">Any serializable exception</span></span>|<span data-ttu-id="fb7cc-131">FaultContract\<TDetail></span><span class="sxs-lookup"><span data-stu-id="fb7cc-131">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="fb7cc-132">Clientproxyobjekte</span><span class="sxs-lookup"><span data-stu-id="fb7cc-132">Client proxy objects</span></span>|<span data-ttu-id="fb7cc-133">Stark typisierte transparente Proxys werden automatisch über MarshalByRefObjects erstellt</span><span class="sxs-lookup"><span data-stu-id="fb7cc-133">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="fb7cc-134">Stark typisierte Proxys werden generiert, bei Bedarf über ChannelFactory\<TChannel ></span><span class="sxs-lookup"><span data-stu-id="fb7cc-134">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="fb7cc-135">Plattform erforderlich</span><span class="sxs-lookup"><span data-stu-id="fb7cc-135">Platform required</span></span>|<span data-ttu-id="fb7cc-136">Client und Server müssen Microsoft-Betriebssystem und .NET verwenden</span><span class="sxs-lookup"><span data-stu-id="fb7cc-136">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="fb7cc-137">Plattformübergreifend</span><span class="sxs-lookup"><span data-stu-id="fb7cc-137">Cross-platform</span></span>|  
|<span data-ttu-id="fb7cc-138">Nachrichtenformat</span><span class="sxs-lookup"><span data-stu-id="fb7cc-138">Message format</span></span>|<span data-ttu-id="fb7cc-139">Private</span><span class="sxs-lookup"><span data-stu-id="fb7cc-139">Private</span></span>|<span data-ttu-id="fb7cc-140">Industriestandards (SOAP, WS-\* usw.)</span><span class="sxs-lookup"><span data-stu-id="fb7cc-140">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="fb7cc-141">Serverimplementierung im Vergleich</span><span class="sxs-lookup"><span data-stu-id="fb7cc-141">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="fb7cc-142">Erstellen eines Servers in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="fb7cc-142">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="fb7cc-143">.NET Remoting-Servertypen müssen von MarshalByRefObject abgeleitet werden und Methoden definieren, die der Client aufrufen kann. Dies wird nachfolgend gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-143">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="fb7cc-144">Die öffentlichen Methoden dieses Servertyps werden zum öffentlichen Vertrag, der für Clients zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-144">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="fb7cc-145">Es gibt keine Trennung zwischen der öffentlichen Serverschnittstelle und deren Implementierung – beide werden durch einen Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-145">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="fb7cc-146">Nachdem der Servertyp definiert wurde, kann er für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-146">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),   
    "RemotingServer",   
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="fb7cc-147">Es gibt viele Möglichkeiten, den Remoting-Typ als Server verfügbar zu machen, einschließlich der Verwendung von Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-147">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="fb7cc-148">Dies ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-148">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="fb7cc-149">Erstellen eines Servers in WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-149">Creating a Server in WCF</span></span>  
 <span data-ttu-id="fb7cc-150">Der entsprechende Schritt in WCF umfasst das Erstellen von zwei Typen – des öffentlichen "Dienstvertrags" und der konkreten Implementierung.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-150">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="fb7cc-151">Der erste Typ wird als eine mit [ServiceContract] markierte Schnittstelle deklariert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-151">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="fb7cc-152">Für Clients verfügbare Methoden sind mit [OperationContract] markiert:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-152">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="fb7cc-153">Die serverseitige Implementierung ist in einer separaten konkreten Klasse definiert, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-153">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="fb7cc-154">Sobald diese Typen definiert wurden, kann der WCF-Server für Clients verfügbar gemacht werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-154">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="fb7cc-155">Es wird in beiden Fällen TCP verwendet, um die Beispiele so ähnlich wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-155">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="fb7cc-156">Beispiele mit Verwendung von HTTP finden Sie weiter unten in diesem Thema in den Szenariobeschreibungen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-156">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="fb7cc-157">Es gibt viele Möglichkeiten zum Konfigurieren und Hosten von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-157">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="fb7cc-158">Dies ist lediglich ein Beispiel, bezeichnet als "selbst gehosteter Dienst".</span><span class="sxs-lookup"><span data-stu-id="fb7cc-158">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="fb7cc-159">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-159">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="fb7cc-160">Vorgehensweise: Definieren eines Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="fb7cc-160">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
- [<span data-ttu-id="fb7cc-161">Konfigurieren von Diensten mit Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="fb7cc-161">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
- [<span data-ttu-id="fb7cc-162">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="fb7cc-162">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="fb7cc-163">Clientimplementierung im Vergleich</span><span class="sxs-lookup"><span data-stu-id="fb7cc-163">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="fb7cc-164">Erstellen eines Clients in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="fb7cc-164">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="fb7cc-165">Sobald ein .NET Remoting-Serverobjekt verfügbar gemacht wurde, kann es von Clients genutzt werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-165">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="fb7cc-166">Die von Activator.GetObject() zurückgegebene RemotingServer-Instanz wird als "transparenter Proxy" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-166">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="fb7cc-167">Diese Instanz implementiert die öffentliche API für den RemotingServer-Typ auf dem Client, sämtliche Methoden rufen jedoch das Serverobjekt auf, das in einem anderen Prozess oder auf einem anderen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-167">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="fb7cc-168">Erstellen eines Clients in WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-168">Creating a Client in WCF</span></span>  
 <span data-ttu-id="fb7cc-169">Der entsprechende Schritt in WCF umfasst die Verwendung einer Kanalfactory zur expliziten Erstellung des Proxys.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-169">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="fb7cc-170">Wie Remoting kann das Proxyobjekt zum Auslösen von Vorgängen auf dem Server verwendet werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-170">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="fb7cc-171">Dieses Beispiel zeigt die Programmierung auf Kanalebene, da sie dem Remoting-Beispiel am ähnlichsten ist.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-171">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="fb7cc-172">Auch verfügbar ist die **Hinzufügen eines Dienstverweises** Ansatz in Visual Studio, der Code zur Vereinfachung der Clientprogrammierung generiert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-172">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="fb7cc-173">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-173">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="fb7cc-174">Clientprogrammierung auf Kanalebene</span><span class="sxs-lookup"><span data-stu-id="fb7cc-174">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
- [<span data-ttu-id="fb7cc-175">Vorgehensweise: Hinzufügen, aktualisieren oder Entfernen eines Dienstverweises</span><span class="sxs-lookup"><span data-stu-id="fb7cc-175">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="fb7cc-176">Verwenden der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="fb7cc-176">Serialization Usage</span></span>  
 <span data-ttu-id="fb7cc-177">Sowohl .NET Remoting als auch WCF verwenden Serialisierung, um Objekte zwischen Client und Server zu senden. Es gelten jedoch folgende wichtige Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-177">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1. <span data-ttu-id="fb7cc-178">Sie verwenden verschiedene Serialisierer und Konventionen, um anzugeben, was serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-178">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2. <span data-ttu-id="fb7cc-179">.NET Remoting unterstützt die Serialisierung "nach Verweis", bei der ein Methoden- oder Eigenschaftenzugriff auf einer Ebene die Ausführung von Code auf einer anderen Ebene zulässt, also über Sicherheitsgrenzen hinweg.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-179">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="fb7cc-180">Diese Funktion birgt Sicherheitsrisiken und ist einer der Hauptgründe dafür, warum Remoting-Endpunkte niemals für nicht vertrauenswürdige Clients verfügbar gemacht werden sollten.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-180">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3. <span data-ttu-id="fb7cc-181">Die von Remoting eingesetzte Serialisierung erfolgt nach dem Ausschlussverfahren (expliziter Ausschluss der Elemente, die nicht serialisiert werden sollen), WCF verwendet eine Serialisierung nach dem Einschlussverfahren (explizite Markierung der Elemente, die serialisiert werden sollen).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-181">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="fb7cc-182">Serialisierung in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="fb7cc-182">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="fb7cc-183">.NET Remoting unterstützt zwei Möglichkeiten zum Serialisieren und Deserialisieren von Objekten zwischen Client und Server:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-183">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
- <span data-ttu-id="fb7cc-184">*Nach Wert* – die Werte des Objekts werden über Ebenengrenzen hinweg serialisiert, und eine neue Instanz dieses Objekts wird auf der anderen Ebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-184">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="fb7cc-185">Alle Aufrufe von Methoden oder Eigenschaften der neuen Instanz werden ausschließlich lokal ausgeführt und wirken sich nicht auf das ursprüngliche Objekt oder die ursprüngliche Ebene aus.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-185">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
- <span data-ttu-id="fb7cc-186">*Als Verweis* – ein spezieller "Objektverweis" über Ebenengrenzen hinweg serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-186">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="fb7cc-187">Wenn eine Ebene mit Methoden oder Eigenschaften des Objekts interagiert, erfolgt die Kommunikation zurück an das ursprüngliche Objekt oder die ursprüngliche Ebene.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-187">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="fb7cc-188">Als-Verweis-Objekte können in beide Richtungen übertragen werden – vom Server an den Client oder vom Client an den Server.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-188">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="fb7cc-189">Als-Wert-Typen werden in Remoting mit dem [Serializable]-Attribut gekennzeichnet oder implementieren "ISerializable", wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-189">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="fb7cc-190">Als Verweis-Typen werden von der MarshalByRefObject-Klasse abgeleitet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-190">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="fb7cc-191">Es ist äußerst wichtig, die Auswirkung von Verweisobjekten in Remoting zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-191">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="fb7cc-192">Wenn eine der beiden Ebenen (Client oder Server) ein Verweisobjekt an die andere Ebene sendet, werden alle Methodenaufrufe auf der Ebene ausgeführt, zu der das Objekt gehört.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-192">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="fb7cc-193">Beispiel: Wenn ein Client Methoden für ein vom Server zurückgegebenes Verweisobjekt aufruft, führt dies zur Ausführung von Code auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-193">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="fb7cc-194">Auf ähnliche Weise wird beim Aufruf von durch den Client bereitgestellten Verweisobjekten durch den Server Code auf dem Client ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-194">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="fb7cc-195">Aus diesem Grund empfiehlt sich die Verwendung von .NET Remoting nur in vollständig vertrauenswürdigen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-195">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="fb7cc-196">Das Offenlegen eines öffentlichen .NET Remoting-Endpunkts für nicht vertrauenswürdige Clients macht einen Remoting-Server anfällig für Angriffe.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-196">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="fb7cc-197">Serialisierung in WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-197">Serialization in WCF</span></span>  
 <span data-ttu-id="fb7cc-198">WCF unterstützt nur die Serialisierung nach Wert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-198">WCF supports only by-value serialization.</span></span> <span data-ttu-id="fb7cc-199">Die gängigste Methode zum Definieren eines Typs für den Austausch zwischen Client und Server wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-199">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="fb7cc-200">Das [DataContract]-Attribut gibt an, dass dieser Typ zwischen Client und Server serialisiert und deserialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-200">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="fb7cc-201">Das Attribut [DataMember] identifiziert die einzelnen Eigenschaften oder Felder für die Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-201">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="fb7cc-202">Wenn WCF ein Objekt über Ebenen hinweg sendet, werden nur die Werte serialisiert, und es wird eine neue Instanz des Objekts auf der anderen Ebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-202">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="fb7cc-203">Sämtliche Interaktionen mit den Werten des Objekts erfolgen nur lokal – es findet im Gegensatz zu den Als-Verweis-Objekten in .NET Remoting keine Kommunikation mit der anderen Ebene statt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-203">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="fb7cc-204">Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](./feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-204">For more information, see [Serialization and Deserialization](./feature-details/serialization-and-deserialization.md).</span></span>  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="fb7cc-205">Funktionen für die Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="fb7cc-205">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="fb7cc-206">Ausnahmen in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="fb7cc-206">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="fb7cc-207">Von einem Remoting-Server ausgelöste Ausnahmen werden serialisiert, an den Client gesendet und lokal auf dem Client wie jede andere Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-207">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="fb7cc-208">Benutzerdefinierte Ausnahmen können durch das Erstellen einer Unterklasse für den Ausnahmetyp und Markierung mit [Serializable] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-208">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="fb7cc-209">Die meisten Framework-Ausnahmen sind bereits in dieser Weise markiert. Deshalb können die meisten von ihnen durch den Server ausgelöst, serialisiert und erneut auf dem Client ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-209">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="fb7cc-210">Wenngleich dieses Design bei der Entwicklung praktisch ist, werden so möglicherweise unbeabsichtigt Informationen gegenüber dem Client offengelegt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-210">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="fb7cc-211">Dies ist einer der vielen Gründe, aus denen Remoting nur in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-211">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="fb7cc-212">Ausnahmen und Fehler in WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-212">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="fb7cc-213">WCF lässt keine Rückgabe zufälliger Ausnahmetypen vom Server an den Client zu, da dies zu einer unbeabsichtigten Offenlegung von Informationen führen kann.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-213">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="fb7cc-214">Wenn ein Dienstvorgang eine unerwartete Ausnahme ausgelöst wird, führt dies dazu, dass auf dem Client eine allgemeine FaultException ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-214">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="fb7cc-215">Diese Ausnahme enthält keinerlei Informationen dazu, warum oder wo das Problem aufgetreten ist, und für einige Anwendungen reicht dies aus.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-215">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="fb7cc-216">Anwendungen, die ausführlichere Fehlerinformationen an den Client kommunizieren müssen, definieren zu diesem Zweck einen Fehlervertrag.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-216">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="fb7cc-217">Hierzu erstellen Sie zunächst einen [DataContract]-Typ, der die Fehlerinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-217">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="fb7cc-218">Geben Sie den Fehlervertrag an, der für jeden Dienstvorgang zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-218">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="fb7cc-219">Der Server meldet Fehlerbedingungen durch das Auslösen einer FaultException.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-219">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 <span data-ttu-id="fb7cc-220">Und wenn der Client eine Anforderung an den Server sendet, können Fehler als normale Ausnahmen abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-220">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 <span data-ttu-id="fb7cc-221">Weitere Informationen zu Fehlerverträgen finden Sie unter <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-221">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="fb7cc-222">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="fb7cc-222">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="fb7cc-223">Sicherheit in .NET Remoting</span><span class="sxs-lookup"><span data-stu-id="fb7cc-223">Security in .NET Remoting</span></span>  
 <span data-ttu-id="fb7cc-224">Einige .NET Remoting-Kanäle unterstützen Sicherheitsfunktionen wie beispielsweise Authentifizierung und Verschlüsselung auf Kanalebene (IPC und TCP).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-224">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="fb7cc-225">Der HTTP-Kanal nutzt sowohl für die Authentifizierung als auch für die Verschlüsselung Internetinformationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-225">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="fb7cc-226">Trotz dieser Unterstützung sollten Sie .NET Remoting als unsicheres Kommunikationsprotokoll betrachten und nur in vollständig vertrauenswürdigen Umgebungen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-226">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="fb7cc-227">Machen Sie niemals einen öffentlichen Remoting-Endpunkt für das Internet oder nicht vertrauenswürdige Clients verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-227">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="fb7cc-228">Sicherheit in WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-228">Security in WCF</span></span>  
 <span data-ttu-id="fb7cc-229">WCF wurde unter dem Gesichtspunkt der Sicherheit entworfen, teilweise auch deshalb, um die Schwachstellen in .NET Remoting zu beheben.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-229">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="fb7cc-230">WCF bietet Sicherheit auf Transport- und Nachrichtenebene und bietet zahlreiche Optionen für Authentifizierung, Autorisierung, Verschlüsselung usw.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-230">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="fb7cc-231">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-231">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="fb7cc-232">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fb7cc-232">Security</span></span>](./feature-details/security.md)  
  
- [<span data-ttu-id="fb7cc-233">WCF-Sicherheitsleitfaden</span><span class="sxs-lookup"><span data-stu-id="fb7cc-233">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="fb7cc-234">Migration nach WCF</span><span class="sxs-lookup"><span data-stu-id="fb7cc-234">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="fb7cc-235">Welche Vorteile bietet die Migration von Remoting nach WCF?</span><span class="sxs-lookup"><span data-stu-id="fb7cc-235">Why Migrate from Remoting to WCF?</span></span>  
  
- <span data-ttu-id="fb7cc-236">**.NET Remoting ist ein legacy-Produkt.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-236">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="fb7cc-237">Siehe [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), es wird ein legacy-Produkt betrachtet und nicht für die neue Entwicklung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-237">As described in [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="fb7cc-238">Für neue und vorhandene Anwendungen wird der Einsatz von WCF oder ASP.NET-Web-API empfohlen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-238">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
- <span data-ttu-id="fb7cc-239">**WCF verwendet plattformübergreifende Standards.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-239">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="fb7cc-240">WCF wurde unter dem Gesichtspunkt einer plattformübergreifenden Interoperabilität entwickelt und unterstützt zahlreiche Industriestandards (SOAP, WS-Security, WS-Trust, usw.).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-240">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="fb7cc-241">Ein WCF-Dienst kann mit Clients interagieren, auf denen andere Betriebssysteme als Windows ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-241">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="fb7cc-242">Remoting wurde in erster Linie für Umgebungen entwickelt, in denen sowohl die Server- als auch die Clientanwendungen mithilfe von .NET Framework auf einem Windows-Betriebssystem ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-242">Remoting was designed primarily for environments where both the server and client applications run using the .NET framework on a Windows operating system.</span></span>  
  
- <span data-ttu-id="fb7cc-243">**WCF bietet integrierte Sicherheit.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-243">**WCF has built-in security.**</span></span> <span data-ttu-id="fb7cc-244">WCF wurde unter Berücksichtigung von Sicherheitsaspekten entworfen und bietet viele Optionen für die Authentifizierung, die Sicherheit auf Transport- und Nachrichtenebene usw. Remoting wurde entworfen, um die Interoperabilität von Anwendungen zu vereinfachen, die Sicherheit in nicht vertrauenswürdigen Umgebungen ist jedoch nicht gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-244">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="fb7cc-245">WCF wurde entworfen, um sowohl in vertrauenswürdigen als auch in nicht vertrauenswürdigen Umgebungen eingesetzt zu werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-245">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="fb7cc-246">Empfehlungen für die Migration</span><span class="sxs-lookup"><span data-stu-id="fb7cc-246">Migration Recommendations</span></span>  
 <span data-ttu-id="fb7cc-247">Für die Migration von .NET Remoting nach WCF werden die folgenden Schritte empfohlen:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-247">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
- <span data-ttu-id="fb7cc-248">**Erstellen des Dienstvertrags.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-248">**Create the service contract.**</span></span> <span data-ttu-id="fb7cc-249">Definieren Sie Ihre Dienstschnittstellentypen, und markieren Sie diese mit dem [ServiceContract]-Attribut. Markieren Sie alle Methoden, die der Client mit [OperationContract] aufrufen darf.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-249">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
- <span data-ttu-id="fb7cc-250">**Erstellen des Datenvertrags an.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-250">**Create the data contract.**</span></span> <span data-ttu-id="fb7cc-251">Definieren Sie die Datentypen, die zwischen Server und Client ausgetauscht werden, und markieren Sie diese mit dem Attribut [DataContract].</span><span class="sxs-lookup"><span data-stu-id="fb7cc-251">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="fb7cc-252">Markieren Sie alle Felder und Eigenschaften, die der Client mit [DataMember] verwenden darf.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-252">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
- <span data-ttu-id="fb7cc-253">**Erstellen des fehlervertrags (optional).**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-253">**Create the fault contract (optional).**</span></span> <span data-ttu-id="fb7cc-254">Erstellen Sie die Typen, die zwischen Server und Client ausgetauscht werden, wenn Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-254">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="fb7cc-255">Markieren Sie diese Typen mit [DataContract] und [DataMember], um sie serialisierbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-255">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="fb7cc-256">Markieren Sie alle Dienstvorgänge, die Sie mit [OperationContract] markiert haben, auch mit [FaultContract], um die Fehler festzulegen, die zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-256">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
- <span data-ttu-id="fb7cc-257">**Konfigurieren Sie und hosten Sie den Dienst.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-257">**Configure and host the service.**</span></span> <span data-ttu-id="fb7cc-258">Sobald der Dienstvertrag erstellt wurde, besteht der nächste Schritt darin, eine Bindung zu konfigurieren, die für den Dienst an einem Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-258">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="fb7cc-259">Weitere Informationen finden Sie unter [Endpunkte: Adressen, Bindungen und Verträge](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-259">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="fb7cc-260">Nach der Migration einer Remoting-Anwendung nach WCF ist es wichtig, Abhängigkeiten mit .NET Remoting zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-260">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="fb7cc-261">Auf diese Weise wird sichergestellt, dass alle Remoing-Sicherheitsanfälligkeiten aus der Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-261">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="fb7cc-262">Folgende Schritte müssen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-262">These steps include the following:</span></span>  
  
- <span data-ttu-id="fb7cc-263">**Beenden Sie die Verwendung von MarshalByRefObject.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-263">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="fb7cc-264">Der MarshalByRefObject-Typ ist nur in Remoting vorhanden und wird von WCF nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-264">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="fb7cc-265">Alle Anwendungstypen, die Unterklassen von MarshalByRefObject verwenden, sollten entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-265">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
- <span data-ttu-id="fb7cc-266">**Beenden Sie die Verwendung von [Serializable] und ISerializable.**</span><span class="sxs-lookup"><span data-stu-id="fb7cc-266">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="fb7cc-267">Das [Serializable]-Attribut und die ISerializable-Schnittstelle wurden ursprünglich zum Serialisieren von Typen in vertrauenswürdigen Umgebungen entworfen und werden von Remoting verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-267">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="fb7cc-268">Die WCF-Serialisierung beruht auf Typen, die mit [DataContract] und [DataMember] markiert sind.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-268">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="fb7cc-269">Die von einer Anwendung verwendeten Datentypen sollten geändert werden, um [DataContract] zu verwenden und nicht ISerializable oder [Serializable].</span><span class="sxs-lookup"><span data-stu-id="fb7cc-269">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="fb7cc-270">Migrationsszenarien</span><span class="sxs-lookup"><span data-stu-id="fb7cc-270">Migration Scenarios</span></span>  
 <span data-ttu-id="fb7cc-271">Betrachten wir nun, wie die folgenden gängigen Remoting-Szenarien in WCF realisiert werden:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-271">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1. <span data-ttu-id="fb7cc-272">Server gibt ein Objekt als Wert an den Client zurück</span><span class="sxs-lookup"><span data-stu-id="fb7cc-272">Server returns an object by-value to the client</span></span>  
  
2. <span data-ttu-id="fb7cc-273">Server gibt ein Objekt als Verweis an den Client zurück</span><span class="sxs-lookup"><span data-stu-id="fb7cc-273">Server returns an object by-reference to the client</span></span>  
  
3. <span data-ttu-id="fb7cc-274">Client sendet ein Objekt als Wert an den Server</span><span class="sxs-lookup"><span data-stu-id="fb7cc-274">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb7cc-275">Das Senden eines Objekts als Verweis vom Client an den Server ist in WCF nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-275">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="fb7cc-276">Nehmen Sie beim Durcharbeiten dieser Szenarien an, dass die Baseline-Schnittstellen für .NET Remoting wie im folgenden Beispiel aussehen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-276">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="fb7cc-277">Die .NET Remoting-Implementierung ist hier nicht wichtig, da nur dargestellt werden soll, wie WCF zur Implementierung einer äquivalenten Funktionalität genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-277">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="fb7cc-278">Szenario 1: Dienst gibt ein Objekt per Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-278">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="fb7cc-279">In diesem Szenario wird gezeigt, wie ein Server ein Objekt per Wert an den Client zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-279">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="fb7cc-280">WCF gibt Objekte immer per Wert an den Server zurück, daher beschreiben die folgenden Schritte lediglich, wie ein normaler WCF-Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-280">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1. <span data-ttu-id="fb7cc-281">Zuerst definieren Sie eine öffentliche Schnittstelle für den WCF-Dienst und markieren ihn mit dem [ServiceContract]-Attribut.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-281">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="fb7cc-282">[OperationContract] wird verwendet, um die serverseitigen Methoden zu identifizieren, die der Client aufruft.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-282">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. <span data-ttu-id="fb7cc-283">Im nächsten Schritt wird der Datenvertrag für diesen Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-283">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="fb7cc-284">Dazu werden Klassen (keine Schnittstellen) erstellt, die mit dem [DataContract]-Attribut markiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-284">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="fb7cc-285">Die einzelnen Eigenschaften oder Felder, die für Client und Server sichtbar sein sollen, werden mit [DataMember] markiert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-285">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="fb7cc-286">Wenn abgeleitete Typen zulässig sein sollen, müssen diese mit dem [KnownType]-Attribut identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-286">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="fb7cc-287">Die einzigen Typen, für die WCF eine Serialisierung oder Deserialisierung zulässt, sind die in der Dienstschnittstelle enthaltenen Typen sowie diese "bekannten Typen".</span><span class="sxs-lookup"><span data-stu-id="fb7cc-287">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="fb7cc-288">Jeder Versuch, andere als in dieser Liste enthaltene Typen zu verwenden, wird zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-288">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer   
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. <span data-ttu-id="fb7cc-289">Als Nächstes stellen wir die Implementierung für die Dienstschnittstelle bereit.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-289">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. <span data-ttu-id="fb7cc-290">Um den WCF-Dienst auszuführen, müssen Sie einen Endpunkt deklarieren, der diese Dienstschnittstelle an einer bestimmten URL über eine bestimmte WCF-Bindung verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-290">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="fb7cc-291">Dies wird üblicherweise erreicht, indem die folgenden Abschnitte in die web.config-Datei des Serverprojekts eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-291">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. <span data-ttu-id="fb7cc-292">Der WCF-Dienst kann anschließend mit dem folgenden Code gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-292">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="fb7cc-293">Wird dieser ServiceHost gestartet, ermittelt er mithilfe der web.config-Datei den richtigen Vertrag sowie die Bindung und den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-293">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="fb7cc-294">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurieren von Diensten mithilfe von Konfigurationsdateien](./configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-294">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="fb7cc-295">Diese Art des Serverstarts wird als Selbsthosting bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-295">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="fb7cc-296">Weitere Informationen zu anderen Optionen zum Hosten von WCF-Diensten finden Sie unter [Hostingdienste](./hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-296">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6. <span data-ttu-id="fb7cc-297">Die Datei „app.config“ des Clientprojekts muss übereinstimmende Bindungsinformationen für den Dienstendpunkt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-297">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="fb7cc-298">Die einfachste Möglichkeit hierzu in Visual Studio ist die Verwendung **Hinzufügen eines Dienstverweises**, die aktualisiert automatisch die Datei "App.config".</span><span class="sxs-lookup"><span data-stu-id="fb7cc-298">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="fb7cc-299">Alternativ können dieselben Änderungen manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-299">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="fb7cc-300">Weitere Informationen zur Verwendung von **Hinzufügen eines Dienstverweises**, finden Sie unter [Vorgehensweise: Hinzufügen, aktualisieren oder Entfernen eines Dienstverweises](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-300">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7. <span data-ttu-id="fb7cc-301">Jetzt können wir den WCF-Dienst vom Client aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-301">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="fb7cc-302">Dazu erstellen wir eine Kanalfactory für diesen Dienst, fordern einen Kanal an und rufen direkt die gewünschte Methode im Kanal auf.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-302">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="fb7cc-303">Dies ist möglich, da der Kanal die Dienstschnittstelle implementiert und die zugrunde liegende Logik für Anforderungen/Antworten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-303">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="fb7cc-304">Der Rückgabewert für diesen Methodenaufruf ist die deserialisierte Kopie der Serverantwort.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-304">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 <span data-ttu-id="fb7cc-305">WCF gibt Objekte vom Server an den Client immer als Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-305">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="fb7cc-306">Die Objekte sind deserialisierte Kopien der Daten, die vom Server gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-306">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="fb7cc-307">Der Client kann Methoden für diese lokalen Kopien aufrufen, ohne Gefahr zu laufen, durch Rückruffunktionen Servercode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-307">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="fb7cc-308">Szenario 2: Server gibt ein Objekt als Verweis zurück.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-308">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="fb7cc-309">Dieses Szenario zeigt, wie der Server ein Objekt als Verweis an den Client zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-309">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="fb7cc-310">In .NET Remoting erfolgt dies für jeden von "MarshalByRefObject" abgeleiteten Typ automatisch, da diese als Verweis serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-310">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="fb7cc-311">Ein Beispiel für dieses Szenario besteht darin, mehreren Clients zu gestatten, unabhängige, sitzungsbasierte, serverseitige Objekte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-311">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="fb7cc-312">Wie bereits erwähnt, gibt der WCF-Dienst Objekte immer als Wert zurück, es gibt also keine direkte Entsprechung für ein Per-Verweis-Objekt. Es ist aber möglich, durch eine Verweissemantik mit Verwendung eines <xref:System.ServiceModel.EndpointAddress10>-Objekts etwas ähnliches zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-312">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="fb7cc-313">Es handelt sich um ein serialisierbares Per-Wert-Objekt, das vom Client dazu verwendet werden kann, ein sitzungsbasiertes Per-Verweis-Objekt auf dem Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-313">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="fb7cc-314">Dadurch wird das Szenario ermöglicht, über mehrere Clients mit unabhängigen, sitzungsbasierten, serverseitigen Objekten zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-314">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1. <span data-ttu-id="fb7cc-315">Zunächst muss ein WCF-Dienstvertrag definiert werden, der dem sitzungsbasierten Objekt selbst entspricht.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-315">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    >  <span data-ttu-id="fb7cc-316">Beachten Sie, dass das sitzungsbasierte Objekt mit [ServiceContract] markiert ist, es handelt sich also um eine normale WCF-Dienstschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-316">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="fb7cc-317">Durch Festlegen der SessionMode-Eigenschaft wird angegeben, dass es sich um einen sitzungsbasierten Dienst handelt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-317">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="fb7cc-318">In WCF ist eine Sitzung eine Möglichkeit, mehrere Nachrichten zuzuordnen, die zwischen zwei Endpunkten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-318">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="fb7cc-319">Dies bedeutet, dass zwischen dem Client und dem Server eine Sitzung eingerichtet wird, sobald der Client eine Verbindung mit diesem Dienst hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-319">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="fb7cc-320">Der Client verwendet eine einzelne eindeutige Instanz des serverseitigen Objekts für alle Interaktionen innerhalb dieser einzelnen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-320">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2. <span data-ttu-id="fb7cc-321">Als Nächstes muss die Implementierung dieser Schnittstelle bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-321">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="fb7cc-322">Durch eine Kennzeichnung mit [ServiceBehavior] und Festlegen von InstanceContextMode wird WCF angewiesen, eine eindeutige Instanz dieses Typs für jede Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-322">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3. <span data-ttu-id="fb7cc-323">Nun benötigen wir eine Möglichkeit, eine Instanz dieses sitzungsbasierten Objekts abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-323">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="fb7cc-324">Hierzu erstellen wir eine weitere WCF-Dienstschnittstelle, die ein EndpointAddress10-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-324">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="fb7cc-325">Dies ist eine serialisierbare Form eines Endpunkts, die vom Server dazu verwendet werden kann, ein sitzungsbasiertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-325">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="fb7cc-326">Und wir implementieren diesen WCF-Dienst:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-326">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =   
               new ChannelFactory<ISessionBoundObject>("sessionbound");  
 
           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="fb7cc-327">Diese Implementierung verwaltet eine Singleton-Kanalfactory, um sitzungsbasierte Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-327">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="fb7cc-328">Beim Aufruf von GetInstanceAddress() werden ein Kanal sowie ein EndpointAddress10-Objekt erstellt, das effektiv auf die diesem Kanal zugeordnete Remoteadresse verweist.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-328">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="fb7cc-329">EndpointAddress10 ist einfach ein Datentyp, der als Wert an den Client zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-329">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4. <span data-ttu-id="fb7cc-330">Die Konfigurationsdatei des Servers muss durch Ausführen von zwei Schritten geändert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-330">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1. <span data-ttu-id="fb7cc-331">Deklarieren Sie eine \<Client >-Abschnitt, der den Endpunkt für das sitzungsbasierte Objekt beschreibt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-331">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="fb7cc-332">Dies ist notwendig, da der Server in diesem Fall auch als Client fungiert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-332">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2. <span data-ttu-id="fb7cc-333">Deklarieren Sie Endpunkte für die Factory und das sitzungsbasierte Objekt.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-333">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="fb7cc-334">Dies ist erforderlich, damit der Client mit den Dienstendpunkten kommunizieren kann, um EndpointAddress10 abzurufen und den sitzungsbasierten Kanal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-334">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="fb7cc-335">Anschließend können diese Dienste gestartet werden:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-335">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. <span data-ttu-id="fb7cc-336">Wir konfigurieren den Client, indem dieselben Endpunkte in der zugehörigen app.config-Datei des Projekts deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-336">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6. <span data-ttu-id="fb7cc-337">Zum Erstellen und Nutzen dieses sitzungsbasierten Objekts muss der Client die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fb7cc-337">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1. <span data-ttu-id="fb7cc-338">Erstellen eines Kanals zum ISessionBoundFactory-Dienst.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-338">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2. <span data-ttu-id="fb7cc-339">Verwenden dieses Kanals, um den Dienst zum Abrufen von EndpointAddress10 aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-339">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3. <span data-ttu-id="fb7cc-340">Verwenden von EndpointAddress10 zum Erstellen eines Kanals für den Abruf eines sitzungsbasierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-340">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4. <span data-ttu-id="fb7cc-341">Interaktion mit dem sitzungsbasierten Objekt, um zu veranschaulichen, dass auch bei mehreren Aufrufen dieselbe Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-341">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =   
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="fb7cc-342">WCF gibt Objekte immer als Wert zurück. Es ist jedoch möglich, die entsprechende Verweissemantik durch Verwenden von EndpointAddress10 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-342">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="fb7cc-343">Dies ermöglicht dem Client, eine sitzungsbasierte WCF-Dienstinstanz anzufordern, um anschließend mit dieser wie mit jedem anderen WCF-Dienst zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-343">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="fb7cc-344">Szenario 3: Client sendet-Server eine per-Wert-Instanz</span><span class="sxs-lookup"><span data-stu-id="fb7cc-344">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="fb7cc-345">Dieses Szenario zeigt, wie der Client eine nicht primitive Objektinstanz als Wert an den Server sendet.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-345">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="fb7cc-346">Da WCF Objekte nur als Wert übergibt, veranschaulicht dieses Szenario die normale WCF-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-346">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1. <span data-ttu-id="fb7cc-347">Verwenden Sie den gleichen WCF-Dienst wie in Szenario 1.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-347">Use the same WCF Service from Scenario 1.</span></span>  
  
2. <span data-ttu-id="fb7cc-348">Verwenden Sie den Client, um ein neues Per-Wert-Objekt (Customer) sowie einen Kanal zur Kommunikation mit dem ICustomerService-Dienst zu erstellen und das Objekt an diesen zu senden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-348">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {   
   FirstName = "Bob",   
   LastName = "Jones",   
   CustomerId = 43,   
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     <span data-ttu-id="fb7cc-349">Das Customer-Objekt wird serialisiert und an den Dienst gesendet und anschließend in eine neue Kopie dieses Objekts deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-349">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb7cc-350">Dieser Code zeigt auch das Senden eines abgeleiteten Typs (PremiumCustomer).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-350">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="fb7cc-351">Die Dienstschnittstelle erwartet ein Customer-Objekt, aber das [KnownType]-Attribut für die Customer-Klasse zeigt an, dass auch PremiumCustomer zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-351">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="fb7cc-352">WCF lässt keine Serialisierung oder Deserialisierung von anderen Typen über diese Dienstschnittstelle zu.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-352">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="fb7cc-353">Der normale WCF-Datenaustausch erfolgt per Wert.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-353">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="fb7cc-354">Auf diese Weise wird sichergestellt, dass Methodenaufrufe für diese Datenobjekte nur lokal erfolgen – es wird kein Code auf der anderen Ebene aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-354">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="fb7cc-355">Es ist zwar möglich, etwa zurückgegebenen per-Verweis-Objekte zu erreichen *aus* dem Server, es ist nicht möglich, ein Client ein Objekt per Verweis übergeben *zu* den Server.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-355">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="fb7cc-356">Ist zwischen Client und Server eine Konversation in beide Richtungen erforderlich, kann dies in WCF mit einem Duplexdienst erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-356">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="fb7cc-357">Weitere Informationen finden Sie unter [Duplexdienste](./feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb7cc-357">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="fb7cc-358">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="fb7cc-358">Summary</span></span>  
 <span data-ttu-id="fb7cc-359">.NET Remoting ist ein Kommunikationsframework, das ausschließlich in vollständig vertrauenswürdigen Umgebungen eingesetzt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-359">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="fb7cc-360">Es handelt sich um ein Legacy-Produkt, das nur zur Bereitstellung von Abwärtskompatibilität unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-360">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="fb7cc-361">Es sollte nicht verwendet werden, um neue Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-361">It should not be used to build new applications.</span></span> <span data-ttu-id="fb7cc-362">Im Gegensatz dazu wurde WCF unter Berücksichtigung von Sicherheitsaspekten entworfen und wird für neue und vorhandene Anwendungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-362">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="fb7cc-363">Microsoft empfiehlt, vorhandene Remoting-Anwendungen zu migrieren, um stattdessen WCF oder die ASP.NET-Web-API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb7cc-363">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>
