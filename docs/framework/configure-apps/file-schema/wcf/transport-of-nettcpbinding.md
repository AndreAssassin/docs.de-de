---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 97139b6bea21e4d908c06f5210e54756865d3c46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217795"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="69533-102">\<transport> of \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="69533-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="69533-103">Definiert den Typ der sicherheitsanforderungen auf Nachrichtenebene für einen Endpunkt konfiguriert, mit der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="69533-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="69533-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="69533-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="69533-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="69533-105">\<bindings></span></span>  
<span data-ttu-id="69533-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="69533-106">\<netTcpBinding></span></span>  
<span data-ttu-id="69533-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="69533-107">\<binding></span></span>  
<span data-ttu-id="69533-108">\<security></span><span class="sxs-lookup"><span data-stu-id="69533-108">\<security></span></span>  
<span data-ttu-id="69533-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="69533-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69533-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="69533-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69533-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-111">Attributes and Elements</span></span>  
 <span data-ttu-id="69533-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69533-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69533-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="69533-113">Attributes</span></span>  
  
|<span data-ttu-id="69533-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="69533-114">Attribute</span></span>|<span data-ttu-id="69533-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69533-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69533-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="69533-116">clientCredentialType</span></span>|<span data-ttu-id="69533-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="69533-117">Optional.</span></span> <span data-ttu-id="69533-118">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69533-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="69533-119">– Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="69533-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="69533-120">– Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="69533-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="69533-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="69533-121">protectionLevel</span></span>|<span data-ttu-id="69533-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="69533-122">Optional.</span></span> <span data-ttu-id="69533-123">Definiert die Sicherheit auf der Ebene des TCP-Transports.</span><span class="sxs-lookup"><span data-stu-id="69533-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="69533-124">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="69533-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="69533-125">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="69533-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="69533-126">Der Standardwert ist `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="69533-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="69533-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="69533-127">sslProtocols</span></span>|<span data-ttu-id="69533-128">Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="69533-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="69533-129">Der Standardwert ist Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="69533-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="69533-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="69533-130">policyEnforcement</span></span>|<span data-ttu-id="69533-131">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="69533-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="69533-132">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="69533-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="69533-133">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69533-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="69533-134">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="69533-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="69533-135">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="69533-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="69533-136">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="69533-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="69533-137">Wert</span><span class="sxs-lookup"><span data-stu-id="69533-137">Value</span></span>|<span data-ttu-id="69533-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69533-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69533-139">Keiner</span><span class="sxs-lookup"><span data-stu-id="69533-139">None</span></span>|<span data-ttu-id="69533-140">Der Client ist anonym.</span><span class="sxs-lookup"><span data-stu-id="69533-140">The client is anonymous.</span></span> <span data-ttu-id="69533-141">Dies erfordert ein Zertifikat für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="69533-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="69533-142">Windows</span><span class="sxs-lookup"><span data-stu-id="69533-142">Windows</span></span>|<span data-ttu-id="69533-143">Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.</span><span class="sxs-lookup"><span data-stu-id="69533-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="69533-144">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="69533-144">Certificate</span></span>|<span data-ttu-id="69533-145">Der Client wird mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="69533-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="69533-146">Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.</span><span class="sxs-lookup"><span data-stu-id="69533-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="69533-147">protectionLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="69533-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="69533-148">Wert</span><span class="sxs-lookup"><span data-stu-id="69533-148">Value</span></span>|<span data-ttu-id="69533-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69533-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69533-150">Keiner</span><span class="sxs-lookup"><span data-stu-id="69533-150">None</span></span>|<span data-ttu-id="69533-151">Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="69533-151">No protection.</span></span>|  
|<span data-ttu-id="69533-152">Sign</span><span class="sxs-lookup"><span data-stu-id="69533-152">Sign</span></span>|<span data-ttu-id="69533-153">Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="69533-153">Messages are signed.</span></span>|  
|<span data-ttu-id="69533-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="69533-154">EncryptAndSign</span></span>|<span data-ttu-id="69533-155">-Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="69533-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69533-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-156">Child Elements</span></span>  
 <span data-ttu-id="69533-157">Keiner</span><span class="sxs-lookup"><span data-stu-id="69533-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69533-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69533-158">Parent Elements</span></span>  
  
|<span data-ttu-id="69533-159">Element</span><span class="sxs-lookup"><span data-stu-id="69533-159">Element</span></span>|<span data-ttu-id="69533-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69533-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69533-161">\<security></span><span class="sxs-lookup"><span data-stu-id="69533-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="69533-162">Gibt an, die Sicherheitsfunktionen des der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="69533-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69533-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69533-163">Remarks</span></span>  
 <span data-ttu-id="69533-164">Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69533-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="69533-165">Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.</span><span class="sxs-lookup"><span data-stu-id="69533-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69533-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69533-166">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="69533-167">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="69533-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="69533-168">Bindungen</span><span class="sxs-lookup"><span data-stu-id="69533-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="69533-169">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="69533-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69533-170">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="69533-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="69533-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="69533-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
