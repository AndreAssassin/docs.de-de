---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: b35e2f365e82291d3f8b827850fdebfe8fa2237d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152840"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="d9103-101">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d9103-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="d9103-102">Definiert eine Bindung für Peerkanal-spezifisches TCP-Messaging.</span><span class="sxs-lookup"><span data-stu-id="d9103-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="d9103-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9103-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9103-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d9103-104">\<bindings></span></span>  
<span data-ttu-id="d9103-105">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d9103-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9103-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9103-106">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9103-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d9103-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d9103-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9103-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9103-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d9103-109">Attributes</span></span>  
  
|<span data-ttu-id="d9103-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d9103-110">Attribute</span></span>|<span data-ttu-id="d9103-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9103-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9103-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="d9103-112">closeTimeout</span></span>|<span data-ttu-id="d9103-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="d9103-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d9103-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="d9103-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9103-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9103-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d9103-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="d9103-116">listenIPAddress</span></span>|<span data-ttu-id="d9103-117">Eine Zeichenfolge mit einer IP-Adresse, die der Peerknoten auf TCP-Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="d9103-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="d9103-118">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="d9103-118">The default is `null`.</span></span>|  
|<span data-ttu-id="d9103-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d9103-119">maxBufferPoolSize</span></span>|<span data-ttu-id="d9103-120">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="d9103-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="d9103-121">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="d9103-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="d9103-122">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="d9103-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="d9103-123">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="d9103-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="d9103-124">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="d9103-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="d9103-125">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="d9103-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="d9103-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d9103-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="d9103-127">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="d9103-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="d9103-128">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="d9103-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="d9103-129">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d9103-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="d9103-130">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="d9103-130">The default is 65536.</span></span>|  
|<span data-ttu-id="d9103-131">Name</span><span class="sxs-lookup"><span data-stu-id="d9103-131">name</span></span>|<span data-ttu-id="d9103-132">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="d9103-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d9103-133">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9103-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d9103-134">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d9103-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d9103-135">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d9103-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="d9103-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="d9103-136">openTimeout</span></span>|<span data-ttu-id="d9103-137">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="d9103-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d9103-138">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="d9103-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9103-139">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9103-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d9103-140">Port</span><span class="sxs-lookup"><span data-stu-id="d9103-140">port</span></span>|<span data-ttu-id="d9103-141">Eine ganze Zahl, die den Netzwerk-Schnittstellenanschluss angibt, an dem diese Bindung TCP-Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d9103-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="d9103-142">Dabei muss es sich um einen Wert zwischen <xref:System.Net.IPEndPoint.MinPort> und <xref:System.Net.IPEndPoint.MaxPort> handeln.</span><span class="sxs-lookup"><span data-stu-id="d9103-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="d9103-143">Der Standard ist 0.</span><span class="sxs-lookup"><span data-stu-id="d9103-143">The default is 0.</span></span>|  
|<span data-ttu-id="d9103-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="d9103-144">receiveTimeout</span></span>|<span data-ttu-id="d9103-145">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="d9103-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d9103-146">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="d9103-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9103-147">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d9103-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="d9103-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="d9103-148">sendTimeout</span></span>|<span data-ttu-id="d9103-149">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="d9103-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d9103-150">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="d9103-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d9103-151">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d9103-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9103-152">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9103-152">Child Elements</span></span>  
  
|<span data-ttu-id="d9103-153">Element</span><span class="sxs-lookup"><span data-stu-id="d9103-153">Element</span></span>|<span data-ttu-id="d9103-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9103-154">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9103-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d9103-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="d9103-156">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="d9103-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d9103-157">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d9103-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="d9103-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="d9103-158">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="d9103-159">Gibt einen Peerresolver an, der von dieser Bindung zum Auflösen einer Peermesh-ID in die Endpunkt-IP-Adressen von Knoten innerhalb des Peermesh verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9103-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="d9103-160">\<security></span><span class="sxs-lookup"><span data-stu-id="d9103-160">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="d9103-161">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d9103-161">Defines the security settings for the message.</span></span> <span data-ttu-id="d9103-162">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d9103-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9103-163">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9103-163">Parent Elements</span></span>  
  
|<span data-ttu-id="d9103-164">Element</span><span class="sxs-lookup"><span data-stu-id="d9103-164">Element</span></span>|<span data-ttu-id="d9103-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9103-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9103-166">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d9103-166">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="d9103-167">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="d9103-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9103-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9103-168">Remarks</span></span>  
 <span data-ttu-id="d9103-169">Diese Bindung bietet Unterstützung für das Erstellen von Peer-to-Peer- oder Mehrparteienanwendungen mithilfe von Peertransport über TCP.</span><span class="sxs-lookup"><span data-stu-id="d9103-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="d9103-170">Jeder Peerknoten kann als Host für mehrere mit diesem Bindungstyp definierte Peerkanäle fungieren.</span><span class="sxs-lookup"><span data-stu-id="d9103-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9103-171">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9103-171">Example</span></span>  
 <span data-ttu-id="d9103-172">Im folgenden Beispiel wird die NetPeerTcpBinding-Bindung veranschaulicht, die Mehrparteienkommunikation über einen Peerkanal ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d9103-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="d9103-173">Ein Szenario mit dieser Bindung, finden Sie unter [Net-Peer-TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="d9103-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="d9103-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9103-174">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="d9103-175">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d9103-175">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d9103-176">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="d9103-176">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d9103-177">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d9103-177">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d9103-178">\<binding></span><span class="sxs-lookup"><span data-stu-id="d9103-178">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- <span data-ttu-id="d9103-179">[NET-Peer-TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d9103-179">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="d9103-180">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="d9103-180">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
