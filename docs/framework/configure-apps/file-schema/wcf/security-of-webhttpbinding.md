---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: b6375a64ea157df01f903901e0414a2989287aee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132292"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="b2d08-102">\<security> of \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b2d08-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="b2d08-103">Gibt an, der die sicherheitsanforderungen für einen Endpunkt konfiguriert, die mit einem [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b2d08-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="b2d08-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b2d08-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2d08-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b2d08-105">\<bindings></span></span>  
<span data-ttu-id="b2d08-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b2d08-106">\<webHttpBinding></span></span>  
<span data-ttu-id="b2d08-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2d08-107">\<binding></span></span>  
<span data-ttu-id="b2d08-108">\<security></span><span class="sxs-lookup"><span data-stu-id="b2d08-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d08-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2d08-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2d08-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2d08-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2d08-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2d08-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2d08-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2d08-112">Attributes</span></span>  
  
|<span data-ttu-id="b2d08-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2d08-113">Attribute</span></span>|<span data-ttu-id="b2d08-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2d08-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2d08-115">Modus</span><span class="sxs-lookup"><span data-stu-id="b2d08-115">mode</span></span>|<span data-ttu-id="b2d08-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2d08-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="b2d08-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="b2d08-117">The default is `None`.</span></span> <span data-ttu-id="b2d08-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b2d08-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b2d08-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="b2d08-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="b2d08-120">Wert</span><span class="sxs-lookup"><span data-stu-id="b2d08-120">Value</span></span>|<span data-ttu-id="b2d08-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2d08-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b2d08-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="b2d08-122">None</span></span>|<span data-ttu-id="b2d08-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2d08-123">Security is disabled.</span></span>|  
|<span data-ttu-id="b2d08-124">Transport</span><span class="sxs-lookup"><span data-stu-id="b2d08-124">Transport</span></span>|<span data-ttu-id="b2d08-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2d08-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="b2d08-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b2d08-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="b2d08-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="b2d08-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="b2d08-128">Die Clientauthentifizierung wird durch die `ClientCredentialType` Attribut der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b2d08-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="b2d08-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="b2d08-129">TransportCredentialOnly</span></span>|<span data-ttu-id="b2d08-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="b2d08-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="b2d08-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b2d08-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="b2d08-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2d08-132">This mode should be used with caution.</span></span> <span data-ttu-id="b2d08-133">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b2d08-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2d08-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2d08-134">Child Elements</span></span>  
  
|<span data-ttu-id="b2d08-135">Element</span><span class="sxs-lookup"><span data-stu-id="b2d08-135">Element</span></span>|<span data-ttu-id="b2d08-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2d08-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d08-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="b2d08-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="b2d08-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="b2d08-138">Defines the transport security settings.</span></span> <span data-ttu-id="b2d08-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="b2d08-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2d08-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2d08-140">Parent Elements</span></span>  
  
|<span data-ttu-id="b2d08-141">Element</span><span class="sxs-lookup"><span data-stu-id="b2d08-141">Element</span></span>|<span data-ttu-id="b2d08-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2d08-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d08-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b2d08-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="b2d08-144">Ein Bindungselement, das verwendet wird, zum Konfigurieren von Endpunkten für Windows Communication Foundation (WCF)-, die auf HTTP-Anforderungen und nicht auf SOAP-Nachrichten reagieren Webdienste.</span><span class="sxs-lookup"><span data-stu-id="b2d08-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2d08-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2d08-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="b2d08-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b2d08-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b2d08-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="b2d08-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b2d08-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2d08-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b2d08-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b2d08-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b2d08-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b2d08-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b2d08-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="b2d08-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="b2d08-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="b2d08-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
