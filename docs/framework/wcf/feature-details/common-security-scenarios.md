---
title: Häufige Sicherheitsszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: af58d6b529fba32380bedb9a892a2b1fd4807d96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857570"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="b9cc9-102">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="b9cc9-102">Common Security Scenarios</span></span>
<span data-ttu-id="b9cc9-103">Die Themen in diesem Abschnitt katalogisieren eine Anzahl möglicher Client- und Dienstsicherheitskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="b9cc9-104">Die Konfigurationen ändern sich aufgrund verschiedenster Faktoren.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="b9cc9-105">Zum Beispiel ob sich ein Dienst oder Client im Intranet befindet oder ob die Sicherheit von Windows oder vom Transport (wie HTTPS) gewährleistet wird.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9cc9-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b9cc9-106">In This Section</span></span>  
 [<span data-ttu-id="b9cc9-107">Internet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="b9cc9-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="b9cc9-108">Ein Beispiel eines öffentlichen, ungesicherten Clients und Diensts.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="b9cc9-109">Intranet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="b9cc9-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="b9cc9-110">Ein grundlegenden Windows Communication Foundation (WCF)-Dienst entwickelt, um Informationen in einem sicheren privaten Netzwerk zu einer WCF-Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="b9cc9-111">Transportsicherheit mit Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="b9cc9-112">Mit dieser Anwendung können sich Clients anhand einer benutzerdefinierten Authentifizierung anmelden.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="b9cc9-113">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="b9cc9-114">Zeigt einen von der Windows-Sicherheit gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="b9cc9-115">Transportsicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="b9cc9-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="b9cc9-116">Dieses Szenario verwendet die Transportsicherheit (wie HTTPS), um Vertraulichkeit und Integrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="b9cc9-117">Transportsicherheit mit Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="b9cc9-118">Zeigt einen mit einem Zertifikat gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="b9cc9-119">Nachrichtensicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="b9cc9-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="b9cc9-120">Zeigt einen Client und-Dienst gesichert durch WCF-nachrichtensicherheit.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="b9cc9-121">Nachrichtensicherheit mit einem Benutzernamenclient</span><span class="sxs-lookup"><span data-stu-id="b9cc9-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="b9cc9-122">Der Client ist eine Windows Forms-Anwendung, mit der sich die Clients mithilfe eines Domänenbenutzernamens und -Kennworts anmelden können.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="b9cc9-123">Nachrichtensicherheit mit einem Zertifikatclient</span><span class="sxs-lookup"><span data-stu-id="b9cc9-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="b9cc9-124">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b9cc9-125">Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="b9cc9-126">Nachrichtensicherheit mit einem Windows-Client</span><span class="sxs-lookup"><span data-stu-id="b9cc9-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="b9cc9-127">Eine Variante des Zertifikatsclients.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-127">A variation of the certificate client.</span></span> <span data-ttu-id="b9cc9-128">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b9cc9-129">Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="b9cc9-130">Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationenaushandlung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="b9cc9-131">Zeigt einen von einer Kerberos-Domäne gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="b9cc9-132">Nachrichtensicherheit mit gegenseitigen Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b9cc9-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="b9cc9-133">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b9cc9-134">Das Serverzertifikat wird mit der Anwendung verteilt und steht außerhalb des Bereichs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="b9cc9-135">Nachrichtensicherheit durch ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="b9cc9-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="b9cc9-136">Verbundsicherheit, die Vertrauenswürdigkeit zwischen unabhängigen Domänen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="b9cc9-137">Vertrauenswürdiges Subsystem</span><span class="sxs-lookup"><span data-stu-id="b9cc9-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="b9cc9-138">Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="b9cc9-139">Die Webdienste greifen auf zusätzliche Ressourcen (z. B. Datenbanken oder andere Webdienste) zu, die gesichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b9cc9-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b9cc9-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="b9cc9-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="b9cc9-141">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b9cc9-141">Related Sections</span></span>  
 [<span data-ttu-id="b9cc9-142">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="b9cc9-143">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9cc9-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="b9cc9-144">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9cc9-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="b9cc9-145">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b9cc9-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="b9cc9-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b9cc9-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="b9cc9-147">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="b9cc9-148">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="b9cc9-149">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="b9cc9-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="b9cc9-150">Überwachung</span><span class="sxs-lookup"><span data-stu-id="b9cc9-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9cc9-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9cc9-151">See also</span></span>

- [<span data-ttu-id="b9cc9-152">Sicherheitsleitfaden und bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="b9cc9-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [<span data-ttu-id="b9cc9-153">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="b9cc9-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
