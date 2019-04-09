---
title: <certificate> Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: eea8130911ca3780a6e4e753c17877e58c50b139
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164267"
---
# <a name="certificate-element"></a><span data-ttu-id="a3b9f-102">\<Zertifikat >-Element</span><span class="sxs-lookup"><span data-stu-id="a3b9f-102">\<certificate> Element</span></span>
<span data-ttu-id="a3b9f-103">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="a3b9f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a3b9f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3b9f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a3b9f-105">\<behaviors></span></span>  
<span data-ttu-id="a3b9f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3b9f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a3b9f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3b9f-107">\<behavior></span></span>  
<span data-ttu-id="a3b9f-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a3b9f-108">\<clientCredentials></span></span>  
<span data-ttu-id="a3b9f-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="a3b9f-109">\<peer></span></span>  
<span data-ttu-id="a3b9f-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="a3b9f-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b9f-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3b9f-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3b9f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3b9f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a3b9f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3b9f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3b9f-114">Attributes</span></span>  
  
|<span data-ttu-id="a3b9f-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3b9f-115">Attribute</span></span>|<span data-ttu-id="a3b9f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3b9f-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a3b9f-117">Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a3b9f-118">Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="a3b9f-119">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a3b9f-120">Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="a3b9f-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a3b9f-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3b9f-122">-LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a3b9f-123">-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a3b9f-124">Die Standardeinstellung ist LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="a3b9f-125">Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="a3b9f-126">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a3b9f-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3b9f-127">-AddressBook: Der Zertifikatspeicher für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a3b9f-128">-   AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="a3b9f-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a3b9f-129">-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).</span><span class="sxs-lookup"><span data-stu-id="a3b9f-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="a3b9f-130">– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a3b9f-131">-Meine: Der Zertifikatspeicher für persönliche Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a3b9f-132">-Stammverzeichnis: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).</span><span class="sxs-lookup"><span data-stu-id="a3b9f-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="a3b9f-133">– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="a3b9f-134">-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="a3b9f-135">Der Standardwert ist My.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="a3b9f-136">Definiert den Typ der X.509-Suche, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a3b9f-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a3b9f-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3b9f-138">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a3b9f-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a3b9f-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a3b9f-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="a3b9f-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a3b9f-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a3b9f-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a3b9f-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="a3b9f-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a3b9f-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a3b9f-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a3b9f-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a3b9f-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a3b9f-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="a3b9f-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a3b9f-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a3b9f-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a3b9f-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="a3b9f-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a3b9f-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a3b9f-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a3b9f-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a3b9f-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a3b9f-149">-   FindByExtension</span></span><br /><span data-ttu-id="a3b9f-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a3b9f-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a3b9f-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a3b9f-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a3b9f-152">Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="a3b9f-153">Der Standardwert ist FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3b9f-154">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3b9f-154">Child Elements</span></span>  
 <span data-ttu-id="a3b9f-155">Keine</span><span class="sxs-lookup"><span data-stu-id="a3b9f-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3b9f-156">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3b9f-156">Parent Elements</span></span>  
  
|<span data-ttu-id="a3b9f-157">Element</span><span class="sxs-lookup"><span data-stu-id="a3b9f-157">Element</span></span>|<span data-ttu-id="a3b9f-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3b9f-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3b9f-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="a3b9f-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a3b9f-160">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3b9f-161">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3b9f-161">Remarks</span></span>  
 <span data-ttu-id="a3b9f-162">Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="a3b9f-163">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a3b9f-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3b9f-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3b9f-164">Example</span></span>  
 <span data-ttu-id="a3b9f-165">Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="a3b9f-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="a3b9f-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3b9f-166">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="a3b9f-167">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="a3b9f-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a3b9f-168">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="a3b9f-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="a3b9f-169">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3b9f-169">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="a3b9f-170">Benutzerdefinierte Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3b9f-170">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="a3b9f-171">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="a3b9f-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
