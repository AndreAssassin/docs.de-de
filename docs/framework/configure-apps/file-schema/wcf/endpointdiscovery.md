---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119495"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="288cd-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="288cd-101">\<endpointDiscovery></span></span>
<span data-ttu-id="288cd-102">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="288cd-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="288cd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="288cd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="288cd-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="288cd-104">\<behaviors></span></span>  
<span data-ttu-id="288cd-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="288cd-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="288cd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="288cd-106">\<behavior></span></span>  
<span data-ttu-id="288cd-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="288cd-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288cd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="288cd-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="288cd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="288cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="288cd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="288cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="288cd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="288cd-111">Attributes</span></span>  
  
|<span data-ttu-id="288cd-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="288cd-112">Attribute</span></span>|<span data-ttu-id="288cd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288cd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="288cd-114">enabled</span><span class="sxs-lookup"><span data-stu-id="288cd-114">enabled</span></span>|<span data-ttu-id="288cd-115">Ein boolescher Wert, der angibt, ob die ermittelbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="288cd-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="288cd-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="288cd-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="288cd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288cd-117">Child Elements</span></span>  
  
|<span data-ttu-id="288cd-118">Element</span><span class="sxs-lookup"><span data-stu-id="288cd-118">Element</span></span>|<span data-ttu-id="288cd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288cd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="288cd-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="288cd-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="288cd-121">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="288cd-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="288cd-122">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="288cd-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="288cd-123">[\<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [von \<EndpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="288cd-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="288cd-124">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="288cd-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="288cd-125">\<types></span><span class="sxs-lookup"><span data-stu-id="288cd-125">\<types></span></span>|<span data-ttu-id="288cd-126">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="288cd-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="288cd-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288cd-127">Parent Elements</span></span>  
  
|<span data-ttu-id="288cd-128">Element</span><span class="sxs-lookup"><span data-stu-id="288cd-128">Element</span></span>|<span data-ttu-id="288cd-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288cd-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="288cd-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="288cd-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="288cd-131">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="288cd-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="288cd-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="288cd-132">Remarks</span></span>  
 <span data-ttu-id="288cd-133">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="288cd-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="288cd-134">Darüber hinaus können Sie die [ \<Bereiche >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)untergeordnetes Element angeben benutzerdefinierter Bereichs-Uris, die verwendet werden kann, um Dienstendpunkte während der Abfrage filtern als auch die [ \<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) untergeordnetes Element, um benutzerdefinierte Metadaten anzugeben, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, ContractTypeName, BindingName, Scope und ListenURI) veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="288cd-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="288cd-135">Dieses Konfigurationselement ist abhängig von der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element, das der dienststeuerungs-Ebene für die Auffindbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="288cd-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="288cd-136">Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) nicht in der Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="288cd-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="288cd-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="288cd-137">Example</span></span>  
 <span data-ttu-id="288cd-138">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="288cd-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="288cd-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="288cd-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
