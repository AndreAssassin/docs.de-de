---
title: <authentication>of <serviceCertificate> -Element
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: d770ba1f9a0a18c927b3a4bf6d4141286e3a380c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919984"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="522a9-102">\<Authentifizierungs > von \<serviceCertificate >-Element</span><span class="sxs-lookup"><span data-stu-id="522a9-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="522a9-103">Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="522a9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="522a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="522a9-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="522a9-105">\<behaviors></span></span>  
<span data-ttu-id="522a9-106">endpointverhaltenbereich</span><span class="sxs-lookup"><span data-stu-id="522a9-106">endpointBehaviors section</span></span>  
<span data-ttu-id="522a9-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="522a9-107">\<behavior></span></span>  
<span data-ttu-id="522a9-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="522a9-108">\<clientCredentials></span></span>  
<span data-ttu-id="522a9-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="522a9-109">\<serviceCertificate></span></span>  
<span data-ttu-id="522a9-110">\<Authentifizierungs ></span><span class="sxs-lookup"><span data-stu-id="522a9-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="522a9-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="522a9-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="522a9-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="522a9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="522a9-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="522a9-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="522a9-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="522a9-114">Attributes</span></span>  
  
|<span data-ttu-id="522a9-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="522a9-115">Attribute</span></span>|<span data-ttu-id="522a9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="522a9-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="522a9-117">customCertificateValidatorType</span></span>|<span data-ttu-id="522a9-118">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="522a9-118">String.</span></span> <span data-ttu-id="522a9-119">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="522a9-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="522a9-120">certificateValidationMode</span></span>|<span data-ttu-id="522a9-121">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="522a9-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="522a9-122">Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="522a9-123">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="522a9-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="522a9-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="522a9-124">revocationMode</span></span>|<span data-ttu-id="522a9-125">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="522a9-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="522a9-126">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="522a9-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="522a9-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="522a9-127">trustedStoreLocation</span></span>|<span data-ttu-id="522a9-128">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="522a9-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="522a9-129">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="522a9-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="522a9-130">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="522a9-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="522a9-131">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="522a9-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="522a9-132">customCertificateValidator-Attribut</span><span class="sxs-lookup"><span data-stu-id="522a9-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="522a9-133">Wert</span><span class="sxs-lookup"><span data-stu-id="522a9-133">Value</span></span>|<span data-ttu-id="522a9-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="522a9-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="522a9-135">String</span></span>|<span data-ttu-id="522a9-136">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="522a9-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="522a9-137">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="522a9-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="522a9-138">Wert</span><span class="sxs-lookup"><span data-stu-id="522a9-138">Value</span></span>|<span data-ttu-id="522a9-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="522a9-140">Enumeration</span><span class="sxs-lookup"><span data-stu-id="522a9-140">Enumeration</span></span>|<span data-ttu-id="522a9-141">Einer der folgenden Werte: "None", "Peer Trust", "ChainTrust", "Peer-orchaintrust", "Custom"</span><span class="sxs-lookup"><span data-stu-id="522a9-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="522a9-142">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="522a9-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="522a9-143">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="522a9-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="522a9-144">Wert</span><span class="sxs-lookup"><span data-stu-id="522a9-144">Value</span></span>|<span data-ttu-id="522a9-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="522a9-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="522a9-146">Enumeration</span></span>|<span data-ttu-id="522a9-147">Einer der folgenden Werte: NOCHECK, Online, offline.</span><span class="sxs-lookup"><span data-stu-id="522a9-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="522a9-148">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="522a9-148">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="522a9-149">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="522a9-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="522a9-150">Wert</span><span class="sxs-lookup"><span data-stu-id="522a9-150">Value</span></span>|<span data-ttu-id="522a9-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="522a9-152">Enumeration</span><span class="sxs-lookup"><span data-stu-id="522a9-152">Enumeration</span></span>|<span data-ttu-id="522a9-153">Einer der folgenden Werte: LocalMachine oder CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="522a9-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="522a9-154">Der Standardwert ist CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="522a9-154">The default is CurrentUser.</span></span> <span data-ttu-id="522a9-155">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="522a9-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="522a9-156">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="522a9-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="522a9-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="522a9-157">Child Elements</span></span>  
 <span data-ttu-id="522a9-158">Keine</span><span class="sxs-lookup"><span data-stu-id="522a9-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="522a9-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="522a9-159">Parent Elements</span></span>  
  
|<span data-ttu-id="522a9-160">Element</span><span class="sxs-lookup"><span data-stu-id="522a9-160">Element</span></span>|<span data-ttu-id="522a9-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="522a9-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="522a9-162">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="522a9-162">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="522a9-163">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="522a9-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="522a9-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="522a9-164">Remarks</span></span>  
 <span data-ttu-id="522a9-165">Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="522a9-166">Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet.</span><span class="sxs-lookup"><span data-stu-id="522a9-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="522a9-167">Dies ist der sicherste Modus.</span><span class="sxs-lookup"><span data-stu-id="522a9-167">This is the most secure mode.</span></span> <span data-ttu-id="522a9-168">Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="522a9-169">Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="522a9-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="522a9-170">Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="522a9-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="522a9-171">Sie können den Wert auch auf `Custom` oder `None` festlegen.</span><span class="sxs-lookup"><span data-stu-id="522a9-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="522a9-172">Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="522a9-173">Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="522a9-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="522a9-174">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)zertifikatvalidator verwendet.</span><span class="sxs-lookup"><span data-stu-id="522a9-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="522a9-175">Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="522a9-176">Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="522a9-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="522a9-177">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="522a9-177">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="522a9-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="522a9-178">Example</span></span>  
 <span data-ttu-id="522a9-179">In folgendem Beispiel werden zwei Aufgaben ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="522a9-179">The following example does two tasks.</span></span> <span data-ttu-id="522a9-180">Zuerst wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen `www.contoso.com` Name sich über dem HTTP-Protokoll befindet, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="522a9-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="522a9-181">Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="522a9-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="522a9-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="522a9-182">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="522a9-183">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="522a9-183">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="522a9-184">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="522a9-184">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="522a9-185">Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes zertifikatvalidator verwendet</span><span class="sxs-lookup"><span data-stu-id="522a9-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="522a9-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="522a9-186">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="522a9-187">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="522a9-187">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="522a9-188">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="522a9-188">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
