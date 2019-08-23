---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: 475c7dfa618cffa70942fc1e02a75910da847701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933087"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="e19be-101">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="e19be-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="e19be-102">Definiert eine Bindung, die sicher und zuverlässig ist und für eine prozessübergreifende Kommunikation auf einem Computer optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="e19be-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="e19be-103">Sie generiert standardmäßig einen Laufzeitkommunikationsstapel mit WS-ReliableMessaging für Verlässlichkeit, Transport- und Übertragungssicherheit, benannte Pipes für den Nachrichtentransport sowie binäre Nachrichtencodierung.</span><span class="sxs-lookup"><span data-stu-id="e19be-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
 <span data-ttu-id="e19be-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e19be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e19be-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e19be-105">\<bindings></span></span>  
<span data-ttu-id="e19be-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="e19be-106">\<netNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19be-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e19be-107">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e19be-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e19be-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e19be-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e19be-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e19be-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e19be-110">Attributes</span></span>  
  
|<span data-ttu-id="e19be-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e19be-111">Attribute</span></span>|<span data-ttu-id="e19be-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e19be-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e19be-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e19be-113">closeTimeout</span></span>|<span data-ttu-id="e19be-114">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e19be-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e19be-115">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e19be-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e19be-116">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e19be-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="e19be-117">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="e19be-117">hostNameComparisonMode</span></span>|<span data-ttu-id="e19be-118">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="e19be-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="e19be-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="e19be-120">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="e19be-121">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="e19be-121">maxBufferPoolSize</span></span>|<span data-ttu-id="e19be-122">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="e19be-122">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="e19be-123">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="e19be-123">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="e19be-124">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="e19be-124">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="e19be-125">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="e19be-125">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="e19be-126">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="e19be-126">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="e19be-127">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="e19be-127">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="e19be-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="e19be-128">maxBufferSize</span></span>|<span data-ttu-id="e19be-129">Eine positive ganze Zahl, die die maximale Größe des Puffers in Bytes angibt, der zum Speichern von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="e19be-130">Falls der Puffer voll ist, verbleiben die überzähligen Daten so lange im zugrunde liegenden Socket, bis der Puffer wieder Platz bietet.</span><span class="sxs-lookup"><span data-stu-id="e19be-130">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="e19be-131">Dieser Wert darf nicht kleiner sein als das `maxReceivedMessageSize`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="e19be-131">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="e19be-132">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="e19be-132">The default is 65536.</span></span> <span data-ttu-id="e19be-133">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="e19be-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="e19be-134">maxConnections</span><span class="sxs-lookup"><span data-stu-id="e19be-134">maxConnections</span></span>|<span data-ttu-id="e19be-135">Eine ganze Zahl, die die maximale Anzahl ausgehender und eingehender Verbindungen angibt, die der Dienst erstellt bzw. akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e19be-135">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="e19be-136">Eingehende und ausgehende Verbindungen werden mit einem separaten, von diesem Attribut angegebenen Grenzwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="e19be-136">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="e19be-137">Eingehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-137">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="e19be-138">Ausgehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-138">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="e19be-139">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="e19be-139">The default is 10.</span></span>|  
|<span data-ttu-id="e19be-140">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="e19be-140">maxReceivedMessageSize</span></span>|<span data-ttu-id="e19be-141">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e19be-141">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="e19be-142">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="e19be-142">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="e19be-143">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="e19be-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="e19be-144">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="e19be-144">The default is 65536.</span></span>|  
|<span data-ttu-id="e19be-145">Name</span><span class="sxs-lookup"><span data-stu-id="e19be-145">name</span></span>|<span data-ttu-id="e19be-146">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="e19be-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e19be-147">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e19be-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e19be-148">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e19be-148">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e19be-149">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e19be-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="e19be-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e19be-150">openTimeout</span></span>|<span data-ttu-id="e19be-151">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e19be-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e19be-152">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e19be-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e19be-153">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e19be-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="e19be-154">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e19be-154">receiveTimeout</span></span>|<span data-ttu-id="e19be-155">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e19be-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e19be-156">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e19be-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e19be-157">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e19be-157">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="e19be-158">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e19be-158">sendTimeout</span></span>|<span data-ttu-id="e19be-159">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e19be-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e19be-160">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e19be-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e19be-161">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e19be-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="e19be-162">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="e19be-162">transactionFlow</span></span>|<span data-ttu-id="e19be-163">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e19be-163">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="e19be-164">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e19be-164">The default is `false`.</span></span>|  
|<span data-ttu-id="e19be-165">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="e19be-165">transactionProtocol</span></span>|<span data-ttu-id="e19be-166">Gibt das Transaktionsprotokoll an, das mit dieser Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e19be-166">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="e19be-167">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e19be-167">Valid values are</span></span><br /><br /> <span data-ttu-id="e19be-168">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="e19be-168">-   OleTransactions</span></span><br /><span data-ttu-id="e19be-169">-WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="e19be-169">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="e19be-170">Der Standardwert ist OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="e19be-170">The default is OleTransactions.</span></span> <span data-ttu-id="e19be-171">Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="e19be-171">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="e19be-172">transferMode</span><span class="sxs-lookup"><span data-stu-id="e19be-172">transferMode</span></span>|<span data-ttu-id="e19be-173">Ein <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e19be-173">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e19be-174">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e19be-174">Child Elements</span></span>  
  
|<span data-ttu-id="e19be-175">Element</span><span class="sxs-lookup"><span data-stu-id="e19be-175">Element</span></span>|<span data-ttu-id="e19be-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e19be-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19be-177">\<security></span><span class="sxs-lookup"><span data-stu-id="e19be-177">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="e19be-178">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="e19be-178">Defines the security settings for the binding.</span></span> <span data-ttu-id="e19be-179">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e19be-179">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|<span data-ttu-id="e19be-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e19be-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e19be-181">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="e19be-181">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e19be-182">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e19be-182">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e19be-183">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e19be-183">Parent Elements</span></span>  
  
|<span data-ttu-id="e19be-184">Element</span><span class="sxs-lookup"><span data-stu-id="e19be-184">Element</span></span>|<span data-ttu-id="e19be-185">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e19be-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19be-186">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e19be-186">\<bindings></span></span>](bindings.md)|<span data-ttu-id="e19be-187">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e19be-187">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e19be-188">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e19be-188">Remarks</span></span>  
 <span data-ttu-id="e19be-189">`NetNamedPipeBinding` generiert standardmäßig eine Laufzeitkommunikation, die Transportsicherheit, Named Pipes zur Nachrichtenübermittlung und eine binäre Nachrichtencodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e19be-189">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="e19be-190">Diese Bindung ist eine entsprechende vom System bereitgestellte Windows Communication Foundation (WCF)-Wahl für die computerinterne Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="e19be-190">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="e19be-191">Sie unterstützt auch Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e19be-191">It also supports transactions.</span></span>  
  
 <span data-ttu-id="e19be-192">Die Standardkonfiguration für `NetNamedPipeBinding` ähnelt der Konfiguration, die von `NetTcpBinding` bereitgestellt wird, sie ist jedoch einfacher, da die WCF-Implementierung nur für die computerinterne Verwendung konzipiert ist und daher weniger Funktionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e19be-192">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="e19be-193">Der wichtigste Unterschied besteht darin, dass die `securityMode`-Einstellung nur die Optionen `None` und `Transport` anbietet.</span><span class="sxs-lookup"><span data-stu-id="e19be-193">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="e19be-194">SOAP-Sicherheitsunterstützung ist keine eingeschlossene Option.</span><span class="sxs-lookup"><span data-stu-id="e19be-194">SOAP security support is not an included option.</span></span> <span data-ttu-id="e19be-195">Das Sicherheitsverhalten ist mit dem optionalen `securityMode`-Attribut konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="e19be-195">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e19be-196">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e19be-196">Example</span></span>  
 <span data-ttu-id="e19be-197">Im folgenden Beispiel wird die netNamedPipeBinding-Bindung, die prozessübergreifende Kommunikation auf dem gleichen Computer bereitstellt, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e19be-197">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="e19be-198">Benannte Pipes funktionieren nicht computerübergreifend.</span><span class="sxs-lookup"><span data-stu-id="e19be-198">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="e19be-199">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="e19be-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="e19be-200">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="e19be-200">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="e19be-201">Wenn Sie die netNamedPipeBinding-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="e19be-201">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="e19be-202">Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs mit einem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="e19be-202">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="e19be-203">In diesem Beispiel wird die Bindungskonfiguration „Binding1“ genannt.</span><span class="sxs-lookup"><span data-stu-id="e19be-203">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e19be-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e19be-204">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="e19be-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="e19be-205">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="e19be-206">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e19be-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e19be-207">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e19be-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e19be-208">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e19be-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
