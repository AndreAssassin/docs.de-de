---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 84a5bc763f898b3d323a6cee468c6e22d27d85a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229601"
---
# <a name="udpbinding"></a><span data-ttu-id="fc856-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="fc856-101">\<udpBinding></span></span>
<span data-ttu-id="fc856-102">Ein Konfigurationselement, das zum Konfigurieren der <xref:System.ServiceModel.UdpBinding>-Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc856-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="fc856-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc856-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc856-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fc856-104">\<bindings></span></span>  
<span data-ttu-id="fc856-105">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="fc856-105">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc856-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc856-106">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc856-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc856-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fc856-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc856-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc856-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc856-109">Attributes</span></span>  
  
|<span data-ttu-id="fc856-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="fc856-110">Attribute</span></span>|<span data-ttu-id="fc856-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc856-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="fc856-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="fc856-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fc856-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fc856-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fc856-114">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="fc856-115">Ein ganzzahliger Wert, der die doppelte Nachrichtenverlaufslänge angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-115">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="fc856-116">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="fc856-116">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="fc856-117">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="fc856-117">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="fc856-118">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="fc856-118">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="fc856-119">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="fc856-119">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="fc856-120">Ein ganzzahliger Wert, der die maximale Anzahl von Nachrichten angibt, die empfangen, jedoch noch nicht aus der Eingangswarteschlange für eine einzelne Kanalinstanz entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="fc856-120">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="fc856-121">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="fc856-121">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="fc856-122">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="fc856-122">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="fc856-123">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="fc856-123">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="fc856-124">Der Standardwert beträgt 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="fc856-124">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="fc856-125">Ein ganzzahliger Wert, der die maximale Anzahl neu zu übermittelnder Nachrichten angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-125">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="fc856-126">Ein ganzzahliger Wert, der die ID der Multicastschnittstelle angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-126">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="fc856-127">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="fc856-127">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="fc856-128">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc856-128">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="fc856-129">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fc856-129">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="fc856-130">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="fc856-130">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="fc856-131">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fc856-131">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="fc856-132">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc856-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="fc856-133">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="fc856-134">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fc856-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fc856-135">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fc856-135">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="fc856-136">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="fc856-137">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fc856-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fc856-138">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="fc856-138">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="fc856-139">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-139">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="fc856-140">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fc856-140">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fc856-141">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fc856-141">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="fc856-142">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc856-142">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="fc856-143">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="fc856-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fc856-144">-BigEndianUnicode: Unicode-BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="fc856-144">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="fc856-145">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="fc856-145">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="fc856-146">-   UTF8: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="fc856-146">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="fc856-147">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="fc856-147">The default is UTF8.</span></span> <span data-ttu-id="fc856-148">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="fc856-148">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="fc856-149">Ein Timespan-Wert, der die Gültigkeitsdauer für die Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="fc856-149">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc856-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc856-150">Child Elements</span></span>  
  
|<span data-ttu-id="fc856-151">Element</span><span class="sxs-lookup"><span data-stu-id="fc856-151">Element</span></span>|<span data-ttu-id="fc856-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc856-152">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc856-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fc856-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="fc856-154">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="fc856-154">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="fc856-155">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="fc856-155">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc856-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc856-156">Parent Elements</span></span>  
  
|<span data-ttu-id="fc856-157">Element</span><span class="sxs-lookup"><span data-stu-id="fc856-157">Element</span></span>|<span data-ttu-id="fc856-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc856-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc856-159">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fc856-159">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="fc856-160">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="fc856-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc856-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc856-161">Remarks</span></span>  
 <span data-ttu-id="fc856-162">UdpBinding ermöglicht WCF-Diensten die Kommunikation über den UDP-Transport.</span><span class="sxs-lookup"><span data-stu-id="fc856-162">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="fc856-163">Sie können für "fire and forget" Nachrichtenaustausch, in denen ein Client sendet eine Nachricht an einen Dienst, und keine Rückantwort erwartet.</span><span class="sxs-lookup"><span data-stu-id="fc856-163">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc856-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc856-164">Example</span></span>  
 <span data-ttu-id="fc856-165">Das folgende Beispiel zeigt, wie Sie konfigurieren die <xref:System.ServiceModel.UdpBinding> mithilfe der <`udpBinding`> Element.</span><span class="sxs-lookup"><span data-stu-id="fc856-165">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>
  <binding  closeTimeout="00:10:00"
            duplicateMessageHistoryLength="100"
            maxBufferPoolSize="100"
            maxPendingMessagesTotalSize="100000"
            maxReceivedMessageSize="65536"
            maxRetransmitCount="10"
            multicastInterfaceId="00000"
            name="myUdpBinding"
            openTimeout="00:10:00"
            receiveTimeout="00:10:00"
            sendTimeout="00:10:00"
            textEncoding="utf-8"
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="fc856-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc856-166">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="fc856-167">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc856-167">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fc856-168">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc856-168">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fc856-169">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fc856-169">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fc856-170">\<binding></span><span class="sxs-lookup"><span data-stu-id="fc856-170">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
