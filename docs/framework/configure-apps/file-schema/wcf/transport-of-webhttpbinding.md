---
title: <transport> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 8dcd51cd248dbba3ccf60295cb1712167684328e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116281"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="040f4-102">\<Transport > von \<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="040f4-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="040f4-103">Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="040f4-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="040f4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="040f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="040f4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="040f4-105">\<bindings></span></span>  
<span data-ttu-id="040f4-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="040f4-106">\<webHttpBinding></span></span>  
<span data-ttu-id="040f4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="040f4-107">\<binding></span></span>  
<span data-ttu-id="040f4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="040f4-108">\<security></span></span>  
<span data-ttu-id="040f4-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="040f4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040f4-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="040f4-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="040f4-111">Typ</span><span class="sxs-lookup"><span data-stu-id="040f4-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="040f4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="040f4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="040f4-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="040f4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="040f4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="040f4-114">Attributes</span></span>  
  
|<span data-ttu-id="040f4-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="040f4-115">Attribute</span></span>|<span data-ttu-id="040f4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="040f4-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="040f4-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="040f4-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="040f4-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="040f4-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="040f4-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="040f4-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="040f4-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="040f4-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="040f4-121">Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="040f4-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="040f4-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="040f4-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="040f4-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="040f4-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="040f4-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="040f4-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="040f4-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="040f4-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="040f4-126">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="040f4-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="040f4-127">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="040f4-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="040f4-128">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="040f4-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="040f4-129">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="040f4-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="040f4-130">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="040f4-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="040f4-131">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="040f4-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="040f4-132">Wert</span><span class="sxs-lookup"><span data-stu-id="040f4-132">Value</span></span>|<span data-ttu-id="040f4-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="040f4-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="040f4-134">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="040f4-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="040f4-135">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="040f4-136">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="040f4-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="040f4-137">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="040f4-138">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="040f4-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="040f4-139">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="040f4-140">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="040f4-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="040f4-141">Wert</span><span class="sxs-lookup"><span data-stu-id="040f4-141">Value</span></span>|<span data-ttu-id="040f4-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="040f4-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="040f4-143">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="040f4-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="040f4-144">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="040f4-145">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="040f4-146">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="040f4-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="040f4-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="040f4-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="040f4-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="040f4-148">Child Elements</span></span>  
 <span data-ttu-id="040f4-149">Keine</span><span class="sxs-lookup"><span data-stu-id="040f4-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="040f4-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="040f4-150">Parent Elements</span></span>  
  
|<span data-ttu-id="040f4-151">Element</span><span class="sxs-lookup"><span data-stu-id="040f4-151">Element</span></span>|<span data-ttu-id="040f4-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="040f4-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="040f4-153">\<security></span><span class="sxs-lookup"><span data-stu-id="040f4-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="040f4-154">Gibt die Sicherheitsfunktionen von der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="040f4-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="040f4-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="040f4-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="040f4-156">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="040f4-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="040f4-157">Bindungen</span><span class="sxs-lookup"><span data-stu-id="040f4-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="040f4-158">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="040f4-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="040f4-159">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="040f4-159">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="040f4-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="040f4-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="040f4-161">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="040f4-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
