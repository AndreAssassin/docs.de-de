---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 5c20baecf3e9fe83385c986e3fb58f0c03eeeb47
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224194"
---
# <a name="knowncertificates"></a><span data-ttu-id="5ffa7-101">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5ffa7-101">\<knownCertificates></span></span>
<span data-ttu-id="5ffa7-102">Gibt eine Auflistung von X.509-Zertifikaten wieder, die zum Authentifizieren von Sicherheitsanmeldeinformationen eines Sicherheitstokendiensts bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="5ffa7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ffa7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ffa7-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5ffa7-104">\<behaviors></span></span>  
<span data-ttu-id="5ffa7-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5ffa7-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5ffa7-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ffa7-106">\<behavior></span></span>  
<span data-ttu-id="5ffa7-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="5ffa7-107">\<serviceCredentials></span></span>  
<span data-ttu-id="5ffa7-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5ffa7-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="5ffa7-109">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5ffa7-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ffa7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ffa7-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ffa7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5ffa7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ffa7-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ffa7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="5ffa7-113">Attributes</span></span>  
 <span data-ttu-id="5ffa7-114">Keine</span><span class="sxs-lookup"><span data-stu-id="5ffa7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ffa7-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ffa7-115">Child Elements</span></span>  
  
|<span data-ttu-id="5ffa7-116">Element</span><span class="sxs-lookup"><span data-stu-id="5ffa7-116">Element</span></span>|<span data-ttu-id="5ffa7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ffa7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ffa7-118">\<add></span><span class="sxs-lookup"><span data-stu-id="5ffa7-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="5ffa7-119">Fügt der Auflistung ein X.509-Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ffa7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ffa7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5ffa7-121">Element</span><span class="sxs-lookup"><span data-stu-id="5ffa7-121">Element</span></span>|<span data-ttu-id="5ffa7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ffa7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ffa7-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5ffa7-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="5ffa7-124">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ffa7-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ffa7-125">Remarks</span></span>  
 <span data-ttu-id="5ffa7-126">Das Szenario für ausgestellte Token weist drei Phasen auf.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="5ffa7-127">In der ersten Phase wird ein Client einen Dienst zugreifen möchten bezeichnet einen *secure token Service*.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5ffa7-128">Der Sicherheitstokendienst authentifiziert den Client und stellt dann ein Token (in der Regel ein SAML-Token (SAML = Security Assertions Markup Language, XML-basierte Auszeichnungssprache für Sicherheitsbestätigungen) für den Client aus.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5ffa7-129">Der Client kehrt dann mit dem Token zum Dienst zurück.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="5ffa7-130">Der Dienst überprüft das Token auf Daten, die ihm die Authentifizierung des Tokens und somit des Clients erlauben.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5ffa7-131">Damit das Token authentifiziert werden kann, muss dem Dienst das vom Sicherheitstokendienst verwendete Zertifikat bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5ffa7-132">Die [ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) Element ist das Repository für die Zertifikate des Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-132">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5ffa7-133">Verwenden Sie zum Hinzufügen von Zertifikaten der [ \<KnownCertificates >-Element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5ffa7-133">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="5ffa7-134">Fügen Sie eine [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) für jedes Zertifikat, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-134">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="5ffa7-135">Standardmäßig müssen die Zertifikate von einem Sicherheitstokendienst bezogen werden.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5ffa7-136">Durch diese "bekannten" Zertifikate wird sichergestellt, dass nur berechtigte Clients auf einen Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5ffa7-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5ffa7-137">Bedingungen, die ein Client von einem Verbunddienst sowie weitere Informationen zur Verwendung dieses Konfigurationselements authentifiziert werden benötigt, finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="5ffa7-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5ffa7-138">Weitere Informationen zu Verbundszenarien finden Sie unter [Verbund und ausgestellte Token](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="5ffa7-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="5ffa7-139">Ein Beispiel, der zum Auffüllen der Auflistung in der Konfiguration veranschaulicht, finden Sie unter [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5ffa7-139">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ffa7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ffa7-140">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="5ffa7-141">\<add></span><span class="sxs-lookup"><span data-stu-id="5ffa7-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="5ffa7-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5ffa7-142">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="5ffa7-143">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="5ffa7-143">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5ffa7-144">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="5ffa7-144">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="5ffa7-145">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="5ffa7-145">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5ffa7-146">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="5ffa7-146">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5ffa7-147">\<add></span><span class="sxs-lookup"><span data-stu-id="5ffa7-147">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="5ffa7-148">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5ffa7-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
