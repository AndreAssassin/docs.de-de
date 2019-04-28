---
title: <peer> der <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783375"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="9deb9-102">\<Peer > des \<ClientCredentials >-Element</span><span class="sxs-lookup"><span data-stu-id="9deb9-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="9deb9-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9deb9-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="9deb9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9deb9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9deb9-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9deb9-105">\<behaviors></span></span>  
<span data-ttu-id="9deb9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9deb9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9deb9-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9deb9-107">\<behavior></span></span>  
<span data-ttu-id="9deb9-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9deb9-108">\<clientCredentials></span></span>  
<span data-ttu-id="9deb9-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="9deb9-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9deb9-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9deb9-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9deb9-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9deb9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9deb9-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9deb9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9deb9-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9deb9-113">Attributes</span></span>  
 <span data-ttu-id="9deb9-114">Keine</span><span class="sxs-lookup"><span data-stu-id="9deb9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9deb9-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9deb9-115">Child Elements</span></span>  
  
|<span data-ttu-id="9deb9-116">Element</span><span class="sxs-lookup"><span data-stu-id="9deb9-116">Element</span></span>|<span data-ttu-id="9deb9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9deb9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9deb9-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="9deb9-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="9deb9-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9deb9-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="9deb9-120">sein.</span><span class="sxs-lookup"><span data-stu-id="9deb9-120">.</span></span>|  
|[<span data-ttu-id="9deb9-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="9deb9-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="9deb9-122">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="9deb9-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="9deb9-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="9deb9-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="9deb9-124">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="9deb9-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9deb9-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9deb9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9deb9-126">Element</span><span class="sxs-lookup"><span data-stu-id="9deb9-126">Element</span></span>|<span data-ttu-id="9deb9-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9deb9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9deb9-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9deb9-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="9deb9-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9deb9-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9deb9-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9deb9-130">Remarks</span></span>  
 <span data-ttu-id="9deb9-131">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9deb9-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="9deb9-132">Weitere Informationen finden Sie unter [Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) und [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9deb9-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9deb9-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9deb9-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="9deb9-134">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="9deb9-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="9deb9-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="9deb9-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- <span data-ttu-id="9deb9-136">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9deb9-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="9deb9-137">[Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9deb9-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="9deb9-138">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="9deb9-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="9deb9-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9deb9-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
