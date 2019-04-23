---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: e26044340bda84fe38b7e286edf833affa94b86c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118211"
---
# <a name="protocolmapping"></a><span data-ttu-id="80acb-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="80acb-101">\<protocolMapping></span></span>
<span data-ttu-id="80acb-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen dar.</span><span class="sxs-lookup"><span data-stu-id="80acb-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="80acb-103">Beim Erstellen von Standardendpunkten zur Laufzeit wird Windows Communication Foundation (WCF) untersucht die konfigurierten Zuordnungen und entscheidet, auf die Bindung für die Verwendung für eine bestimmte Adresse basiert.</span><span class="sxs-lookup"><span data-stu-id="80acb-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="80acb-104">**\<system.serviceModel>**</span><span class="sxs-lookup"><span data-stu-id="80acb-104">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="80acb-105">&nbsp;&nbsp;**\<protocolMapping>**</span><span class="sxs-lookup"><span data-stu-id="80acb-105">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80acb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="80acb-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80acb-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80acb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="80acb-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80acb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80acb-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="80acb-109">Attributes</span></span>  
 <span data-ttu-id="80acb-110">Keine</span><span class="sxs-lookup"><span data-stu-id="80acb-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80acb-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80acb-111">Child Elements</span></span>  
  
|<span data-ttu-id="80acb-112">Element</span><span class="sxs-lookup"><span data-stu-id="80acb-112">Element</span></span>|<span data-ttu-id="80acb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80acb-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80acb-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="80acb-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="80acb-115">Enthält eine standardprotokollzuordnung zwischen einem transportprotokollschema (z. B. http, net.tcp, net.pipe usw.) und einer WCF-Bindung.</span><span class="sxs-lookup"><span data-stu-id="80acb-115">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80acb-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80acb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="80acb-117">Element</span><span class="sxs-lookup"><span data-stu-id="80acb-117">Element</span></span>|<span data-ttu-id="80acb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80acb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80acb-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="80acb-119">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="80acb-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="80acb-120">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80acb-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80acb-121">Example</span></span>  
 <span data-ttu-id="80acb-122">Im folgenden Konfigurationsbeispiel wird die Standardprotokollzuordnung in der Datei machine.config veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="80acb-122">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="80acb-123">Sie können diese Standardzuordnung auf Computerebene überschreiben, indem Sie die Datei machine.config ändern.</span><span class="sxs-lookup"><span data-stu-id="80acb-123">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="80acb-124">Wenn Sie sie lediglich innerhalb des Bereichs einer Anwendung überschreiben möchten, können Sie diesen Abschnitt innerhalb der Anwendungskonfigurationsdatei überschreiben und die Zuordnung für einzelne Protokollschemas ändern.</span><span class="sxs-lookup"><span data-stu-id="80acb-124">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="80acb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80acb-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
