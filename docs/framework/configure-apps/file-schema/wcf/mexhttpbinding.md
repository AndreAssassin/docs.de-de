---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: c6ff5b2cfee1d55b9399b97f3b3397e6bbf8eca2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400242"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="56ff9-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="56ff9-101">\<mexHttpBinding></span></span>
<span data-ttu-id="56ff9-102">Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56ff9-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="56ff9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56ff9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56ff9-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="56ff9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="56ff9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="56ff9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="56ff9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding->**</span><span class="sxs-lookup"><span data-stu-id="56ff9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56ff9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="56ff9-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56ff9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56ff9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="56ff9-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56ff9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56ff9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="56ff9-110">Attributes</span></span>  
  
|<span data-ttu-id="56ff9-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="56ff9-111">Attribute</span></span>|<span data-ttu-id="56ff9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56ff9-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="56ff9-113">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56ff9-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="56ff9-114">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56ff9-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56ff9-115">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56ff9-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="56ff9-116">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="56ff9-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="56ff9-117">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56ff9-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="56ff9-118">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="56ff9-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="56ff9-119">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="56ff9-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="56ff9-120">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="56ff9-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="56ff9-121">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="56ff9-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="56ff9-122">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56ff9-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="56ff9-123">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56ff9-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56ff9-124">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56ff9-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="56ff9-125">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56ff9-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="56ff9-126">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56ff9-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56ff9-127">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="56ff9-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="56ff9-128">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56ff9-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="56ff9-129">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56ff9-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56ff9-130">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56ff9-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56ff9-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56ff9-131">Child Elements</span></span>  
 <span data-ttu-id="56ff9-132">Keine</span><span class="sxs-lookup"><span data-stu-id="56ff9-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56ff9-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56ff9-133">Parent Elements</span></span>  
  
|<span data-ttu-id="56ff9-134">Element</span><span class="sxs-lookup"><span data-stu-id="56ff9-134">Element</span></span>|<span data-ttu-id="56ff9-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56ff9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56ff9-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="56ff9-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="56ff9-137">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="56ff9-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56ff9-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56ff9-138">Remarks</span></span>  
 <span data-ttu-id="56ff9-139">Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung mit deaktivierter Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="56ff9-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="56ff9-140">Sie unterstützt die meisten Metadatenanforderungen.</span><span class="sxs-lookup"><span data-stu-id="56ff9-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ff9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56ff9-141">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="56ff9-142">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="56ff9-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="56ff9-143">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="56ff9-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="56ff9-144">Metadaten</span><span class="sxs-lookup"><span data-stu-id="56ff9-144">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="56ff9-145">Bindungen</span><span class="sxs-lookup"><span data-stu-id="56ff9-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="56ff9-146">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="56ff9-146">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="56ff9-147">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="56ff9-147">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="56ff9-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="56ff9-148">\<binding></span></span>](../../../misc/binding.md)
