---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 538591c85d91960eb4d4fa04caa945954ee5a997
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397704"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="8f222-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="8f222-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="8f222-102">Gibt die Codierungs- und Nachrichtenversionierung an, die für SOAP MTOM-basierte (Message Transmission Optimization Mechanism) Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f222-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
<span data-ttu-id="8f222-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f222-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8f222-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8f222-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f222-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8f222-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="8f222-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8f222-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mtomMessageEncoding->**</span><span class="sxs-lookup"><span data-stu-id="8f222-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f222-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f222-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f222-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f222-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f222-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f222-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f222-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f222-112">Attributes</span></span>  
  
|<span data-ttu-id="8f222-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f222-113">Attribute</span></span>|<span data-ttu-id="8f222-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f222-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f222-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8f222-115">maxBufferSize</span></span>|<span data-ttu-id="8f222-116">Eine ganze Zahl, die die maximale Größe des Puffers angibt.</span><span class="sxs-lookup"><span data-stu-id="8f222-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="8f222-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="8f222-117">maxReadPoolSize</span></span>|<span data-ttu-id="8f222-118">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8f222-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="8f222-119">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="8f222-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8f222-120">Der Standard ist 64.</span><span class="sxs-lookup"><span data-stu-id="8f222-120">The default is 64.</span></span>|  
|<span data-ttu-id="8f222-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="8f222-121">maxWritePoolSize</span></span>|<span data-ttu-id="8f222-122">Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="8f222-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="8f222-123">Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.</span><span class="sxs-lookup"><span data-stu-id="8f222-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="8f222-124">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="8f222-124">The default is 16.</span></span>|  
|<span data-ttu-id="8f222-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="8f222-125">messageVersion</span></span>|<span data-ttu-id="8f222-126">Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f222-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="8f222-127">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="8f222-127">Valid values are</span></span><br /><br /> <span data-ttu-id="8f222-128">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="8f222-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="8f222-129">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="8f222-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="8f222-130">Der Standardwert ist Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="8f222-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="8f222-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="8f222-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="8f222-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="8f222-132">writeEncoding</span></span>|<span data-ttu-id="8f222-133">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f222-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="8f222-134">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="8f222-134">Valid values are</span></span><br /><br /> <span data-ttu-id="8f222-135">UnicodeFffeTextEncoding Unicode bigEndian-Codierung</span><span class="sxs-lookup"><span data-stu-id="8f222-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="8f222-136">Utf16TextEncoding Unicode-Codierung</span><span class="sxs-lookup"><span data-stu-id="8f222-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="8f222-137">Utf8TextEncoding 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="8f222-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="8f222-138">Der Standardwert ist Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="8f222-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="8f222-139">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="8f222-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f222-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f222-140">Child Elements</span></span>  
  
|<span data-ttu-id="8f222-141">Element</span><span class="sxs-lookup"><span data-stu-id="8f222-141">Element</span></span>|<span data-ttu-id="8f222-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f222-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f222-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f222-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="8f222-144">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="8f222-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="8f222-145">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="8f222-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f222-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f222-146">Parent Elements</span></span>  
  
|<span data-ttu-id="8f222-147">Element</span><span class="sxs-lookup"><span data-stu-id="8f222-147">Element</span></span>|<span data-ttu-id="8f222-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f222-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f222-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="8f222-149">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="8f222-150">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="8f222-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f222-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f222-151">Remarks</span></span>  
 <span data-ttu-id="8f222-152">Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.</span><span class="sxs-lookup"><span data-stu-id="8f222-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="8f222-153">Beim Decodieren wird dieser Prozess umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="8f222-153">Decoding is the reverse process.</span></span> <span data-ttu-id="8f222-154">Windows Communication Foundation (WCF) umfasst drei Codierungs Typen für SOAP-Nachrichten: Text, Binär und MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="8f222-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="8f222-155">Das `MtomMessageEncoding`-Element gibt die Zeichencodierung und die für Nachrichten mit MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion und andere Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="8f222-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="8f222-156">MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="8f222-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="8f222-157">Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="8f222-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="8f222-158">Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Konvertierung in ihr base64-verschlüsseltes Format.</span><span class="sxs-lookup"><span data-stu-id="8f222-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f222-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f222-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="8f222-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f222-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="8f222-161">Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="8f222-161">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="8f222-162">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="8f222-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="8f222-163">Bindungen</span><span class="sxs-lookup"><span data-stu-id="8f222-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8f222-164">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="8f222-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8f222-165">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="8f222-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8f222-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8f222-166">\<customBinding></span></span>](custombinding.md)
