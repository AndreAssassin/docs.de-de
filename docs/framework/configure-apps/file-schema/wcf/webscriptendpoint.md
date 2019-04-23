---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105650"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="dbbd1-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="dbbd1-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="dbbd1-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt Bindung, die automatisch die [ \<EnableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="dbbd1-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="dbbd1-103">Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dbbd1-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="dbbd1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dbbd1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dbbd1-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dbbd1-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbbd1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbbd1-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbbd1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dbbd1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dbbd1-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbbd1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbbd1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="dbbd1-109">Attributes</span></span>  
  
|<span data-ttu-id="dbbd1-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="dbbd1-110">Attribute</span></span>|<span data-ttu-id="dbbd1-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbbd1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbbd1-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="dbbd1-112">webEndpointType</span></span>|<span data-ttu-id="dbbd1-113">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="dbbd1-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbbd1-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dbbd1-114">Child Elements</span></span>  
 <span data-ttu-id="dbbd1-115">Keine</span><span class="sxs-lookup"><span data-stu-id="dbbd1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbbd1-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dbbd1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dbbd1-117">Element</span><span class="sxs-lookup"><span data-stu-id="dbbd1-117">Element</span></span>|<span data-ttu-id="dbbd1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbbd1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbbd1-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dbbd1-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="dbbd1-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="dbbd1-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbbd1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbbd1-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
