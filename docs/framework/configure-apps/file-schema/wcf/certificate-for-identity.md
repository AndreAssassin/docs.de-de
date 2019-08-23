---
title: <certificate> für <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 52d1fa31cebd949c91809464976739ef1334af29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919617"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="4c473-102">\<Zertifikat > für \<Identity ></span><span class="sxs-lookup"><span data-stu-id="4c473-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="4c473-103">Gibt ein zum Überprüfen eines Servers an einem Client verwendetes X.509-Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="4c473-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="4c473-104">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4c473-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="4c473-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="4c473-105">\<identity></span></span>  
<span data-ttu-id="4c473-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="4c473-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c473-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c473-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c473-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c473-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4c473-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c473-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c473-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c473-110">Attributes</span></span>  
  
|<span data-ttu-id="4c473-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4c473-111">Attribute</span></span>|<span data-ttu-id="4c473-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c473-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c473-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="4c473-113">encodedValue</span></span>|<span data-ttu-id="4c473-114">Eine Base64-Codierung des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="4c473-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c473-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c473-115">Child Elements</span></span>  
 <span data-ttu-id="4c473-116">Keine</span><span class="sxs-lookup"><span data-stu-id="4c473-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c473-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c473-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4c473-118">Element</span><span class="sxs-lookup"><span data-stu-id="4c473-118">Element</span></span>|<span data-ttu-id="4c473-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c473-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c473-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="4c473-120">\<identity></span></span>](identity.md)|<span data-ttu-id="4c473-121">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="4c473-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c473-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c473-122">Example</span></span>  
 <span data-ttu-id="4c473-123">Im folgenden Code wird die codierte Darstellung eines Zertifikats dargestellt, das zum Überprüfen eines Servers an einem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c473-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4c473-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c473-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="4c473-125">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4c473-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4c473-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="4c473-126">\<identity></span></span>](identity.md)
