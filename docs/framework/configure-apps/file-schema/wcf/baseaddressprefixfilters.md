---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 8a59f651318e18411b1485fc4eebeb7a550afca0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919855"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="3924c-101">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="3924c-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="3924c-102">Stellt eine Auflistung von Konfigurationselementen dar, die Pass-Through-Filter angeben. diese bieten einen Mechanismus zum Auswählen der entsprechenden Internetinformationsdienste (IIS)-Bindungen beim Hosten der Windows Communication Foundation (WCF)-Anwendung in IIS.</span><span class="sxs-lookup"><span data-stu-id="3924c-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3924c-103">\<der baseadressscrifixfilters-> erkennt "localhost" nicht. verwenden Sie stattdessen den voll qualifizierten Computernamen.</span><span class="sxs-lookup"><span data-stu-id="3924c-103">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="3924c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3924c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3924c-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="3924c-105">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3924c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3924c-106">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3924c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3924c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3924c-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3924c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3924c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3924c-109">Attributes</span></span>  
 <span data-ttu-id="3924c-110">Keine</span><span class="sxs-lookup"><span data-stu-id="3924c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3924c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3924c-111">Child Elements</span></span>  
  
|<span data-ttu-id="3924c-112">Element</span><span class="sxs-lookup"><span data-stu-id="3924c-112">Element</span></span>|<span data-ttu-id="3924c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3924c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3924c-114">\<add></span><span class="sxs-lookup"><span data-stu-id="3924c-114">\<add></span></span>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="3924c-115">Fügt ein Konfigurationselement hinzu, das einen Präfixfilter für die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="3924c-115">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3924c-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3924c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3924c-117">Element</span><span class="sxs-lookup"><span data-stu-id="3924c-117">Element</span></span>|<span data-ttu-id="3924c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3924c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3924c-119">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="3924c-119">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="3924c-120">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3924c-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3924c-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3924c-121">Remarks</span></span>  
 <span data-ttu-id="3924c-122">Ein Präfixfilter bietet gemeinsamen Hostanbietern eine Methode, um die vom Dienst zu verwendenden URIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3924c-122">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="3924c-123">Sie ermöglicht es gemeinsamen Hosts, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.</span><span class="sxs-lookup"><span data-stu-id="3924c-123">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="3924c-124">IIS-Websites sind Container für virtuelle Anwendungen, die virtuelle Verzeichnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="3924c-124">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="3924c-125">Auf die Anwendung auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3924c-125">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="3924c-126">IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3924c-126">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="3924c-127">Das Bindungsprotokoll (z.&#160;B. HTTP) definiert das Schema, über das die Kommunikation erfolgt, und Bindungsinformationen (z.&#160;B. IP-Address, Anschluss, Hostheader) enthalten Daten, die für den Zugriff auf die Website verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3924c-127">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="3924c-128">IIS unterstützt die Angabe mehrerer IIS-Bindungen für jede Website, was zu mehreren Basisadressen für jedes Schema führt.</span><span class="sxs-lookup"><span data-stu-id="3924c-128">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="3924c-129">Da ein unter einer Website gehosteter WCF-Dienst nur die Bindung an eine Basisadresse für jedes Schema ermöglicht, können Sie mit der Präfix Filterfunktion die erforderliche Basisadresse des gehosteten Dienstanbieter auswählen.</span><span class="sxs-lookup"><span data-stu-id="3924c-129">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="3924c-130">Die von IIS bereitgestellten eingehenden Basisadressen werden anhand des optionalen Präfixlistenfilters gefiltert.</span><span class="sxs-lookup"><span data-stu-id="3924c-130">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="3924c-131">Ihre Website kann beispielsweise die folgenden Basisadressen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3924c-131">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="3924c-132">Sie können die folgende Konfigurationsdatei verwenden, um einen Präfixfilter auf AppDomain-Ebene anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3924c-132">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="3924c-133">In diesem Beispiel sind `net.tcp://test1.fabrikam.com:8000` und `http://test2.fabrikam.com:9000` die einzigen Basisadressen für die jeweiligen Schemata, die übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="3924c-133">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="3924c-134">Standardmäßig werden alle Adressen übergeben, wenn kein Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3924c-134">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="3924c-135">Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="3924c-135">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3924c-136">Der Filter unterstützt keine Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="3924c-136">The filter does not support any wildcards.</span></span> <span data-ttu-id="3924c-137">Darüber hinaus verfügen die von IIS angegebenen Basisadressen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemata gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="3924c-137">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="3924c-138">Diese Adressen werden nicht herausgefiltert.</span><span class="sxs-lookup"><span data-stu-id="3924c-138">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3924c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3924c-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="3924c-140">Hosting</span><span class="sxs-lookup"><span data-stu-id="3924c-140">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
