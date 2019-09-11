---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: c68cabd03eca71b41a0d0acce26897fa2653f4d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855374"
---
# <a name="dns"></a><span data-ttu-id="72770-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="72770-101">\<dns></span></span>
<span data-ttu-id="72770-102">Gibt die erwartete Identität des Servers an.</span><span class="sxs-lookup"><span data-stu-id="72770-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="72770-103">Diese Identität ist für den X.509-Zertifikat-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="72770-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="72770-104">Sie ist auch für den Windows-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.</span><span class="sxs-lookup"><span data-stu-id="72770-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="72770-105">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="72770-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="72770-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="72770-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="72770-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="72770-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="72770-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="72770-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="72770-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="72770-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="72770-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Identitäts >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="72770-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="72770-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DNS->**</span><span class="sxs-lookup"><span data-stu-id="72770-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72770-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="72770-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72770-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72770-113">Attributes and Elements</span></span>  
 <span data-ttu-id="72770-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72770-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72770-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="72770-115">Attributes</span></span>  
  
|<span data-ttu-id="72770-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="72770-116">Attribute</span></span>|<span data-ttu-id="72770-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72770-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72770-118">Wert</span><span class="sxs-lookup"><span data-stu-id="72770-118">value</span></span>|<span data-ttu-id="72770-119">Der DNS des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="72770-119">The DNS of the certificate.</span></span> <span data-ttu-id="72770-120">DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP-basierten Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="72770-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="72770-121">Benutzer können anzeigen Amen <https://go.microsoft.com/fwlink/?prd=10929> wie oder [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)einfacher als Zahlen basierte Adressen, wie z. b. 207.46.131.137, merken.</span><span class="sxs-lookup"><span data-stu-id="72770-121">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72770-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72770-122">Child Elements</span></span>  
 <span data-ttu-id="72770-123">Keine</span><span class="sxs-lookup"><span data-stu-id="72770-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72770-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72770-124">Parent Elements</span></span>  
  
|<span data-ttu-id="72770-125">Element</span><span class="sxs-lookup"><span data-stu-id="72770-125">Element</span></span>|<span data-ttu-id="72770-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72770-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72770-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="72770-127">\<identity></span></span>](identity.md)|<span data-ttu-id="72770-128">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="72770-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="72770-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72770-129">Example</span></span>  
 <span data-ttu-id="72770-130">Der folgende Konfigurationscode gibt den DNS eines X.509-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="72770-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="72770-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72770-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="72770-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72770-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="72770-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="72770-133">\<identity></span></span>](identity.md)
