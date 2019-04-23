---
title: <clientCertificate> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 26ebac6439a90959e3a926e6a36c9044251a4aae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107983"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="62aec-102">\<clientCertificate> of \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="62aec-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="62aec-103">Definiert ein X.509-Zertifikat, das zum Signieren und Verschlüsseln von Nachrichten an einen Client von einem Dienst in einem Duplexkommunikationsmuster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62aec-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="62aec-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62aec-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62aec-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="62aec-105">\<behaviors></span></span>  
<span data-ttu-id="62aec-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="62aec-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="62aec-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="62aec-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="62aec-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="62aec-108">\<behavior></span></span>  
<span data-ttu-id="62aec-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="62aec-109">\<serviceCredentials></span></span>  
<span data-ttu-id="62aec-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="62aec-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62aec-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="62aec-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62aec-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62aec-112">Attributes and Elements</span></span>  
 <span data-ttu-id="62aec-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62aec-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62aec-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="62aec-114">Attributes</span></span>  
 <span data-ttu-id="62aec-115">Keine</span><span class="sxs-lookup"><span data-stu-id="62aec-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62aec-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62aec-116">Child Elements</span></span>  
  
|<span data-ttu-id="62aec-117">Element</span><span class="sxs-lookup"><span data-stu-id="62aec-117">Element</span></span>|<span data-ttu-id="62aec-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62aec-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62aec-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="62aec-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="62aec-120">Gibt Authentifizierungsoptionen für das Clientzertifikat an.</span><span class="sxs-lookup"><span data-stu-id="62aec-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="62aec-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="62aec-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="62aec-122">Gibt das zu verwendende Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="62aec-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62aec-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62aec-123">Parent Elements</span></span>  
  
|<span data-ttu-id="62aec-124">Element</span><span class="sxs-lookup"><span data-stu-id="62aec-124">Element</span></span>|<span data-ttu-id="62aec-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62aec-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62aec-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="62aec-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="62aec-127">Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="62aec-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62aec-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62aec-128">Remarks</span></span>  
 <span data-ttu-id="62aec-129">Dieses Element wird verwendet, wenn dem Dienst das Zertifikat des Clients im Voraus bekannt sein muss, damit eine sichere Kommunikation mit dem Client stattfinden kann.</span><span class="sxs-lookup"><span data-stu-id="62aec-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="62aec-130">Dies ist bei der Duplexkommunikation der Fall.</span><span class="sxs-lookup"><span data-stu-id="62aec-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="62aec-131">Bei der üblicheren Kommunikation mit Anforderung und Antwort fügt der Client das Zertifikat in die Anforderung ein, das dann wiederum vom Dienst zum Verschlüsseln und Signieren seiner Antwort an den Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62aec-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="62aec-132">Bei der Duplexkommunikation verfügt der Dienst jedoch nicht über eine Anforderung vom Client und benötigt deshalb das Clientzertifikat im Voraus, um die Nachricht an den Client zu sichern.</span><span class="sxs-lookup"><span data-stu-id="62aec-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="62aec-133">Sie müssen deshalb das Zertifikat des Clients in einer Out-of-Band-Aushandlung beziehen und das Zertifikat mit diesem Element angeben.</span><span class="sxs-lookup"><span data-stu-id="62aec-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="62aec-134">Weitere Informationen über duplexdienste finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="62aec-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="62aec-135">Das in diesem Element festgelegte Zertifikat wird nur bei Bindungen, die mit dem `MutualCertificateDuplex`-Authentifizierungsmodus für die Nachrichtensicherheit konfiguriert sind, zum Verschlüsseln von Nachrichten für Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="62aec-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62aec-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62aec-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="62aec-137">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="62aec-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="62aec-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="62aec-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="62aec-139">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="62aec-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
