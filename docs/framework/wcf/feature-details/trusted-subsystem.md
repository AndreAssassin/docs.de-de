---
title: Vertrauenswürdiges Subsystem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f5ce46b-e259-4bc9-a0b9-89d06fc9341c
ms.openlocfilehash: a0f845ad0d8ca461f8ab0b3188a72e87c589add2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319364"
---
# <a name="trusted-subsystem"></a><span data-ttu-id="06368-102">Vertrauenswürdiges Subsystem</span><span class="sxs-lookup"><span data-stu-id="06368-102">Trusted Subsystem</span></span>
<span data-ttu-id="06368-103">Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="06368-103">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="06368-104">Die Webdienste sind so ausgelegt, dass der Zugriff auf zusätzliche Ressourcen (beispielsweise Datenbanken oder andere Webdienste) in der Geschäftslogik des Webdiensts gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="06368-104">The Web services are designed so that access to additional resources (such as databases or other Web services) is encapsulated in the business logic of the Web service.</span></span> <span data-ttu-id="06368-105">Diese Ressourcen müssen vor nicht autorisiertem Zugriff geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="06368-105">These resources must be protected against unauthorized access.</span></span> <span data-ttu-id="06368-106">Die folgende Abbildung stellt einen vertrauenswürdigen Subsystemprozess dar.</span><span class="sxs-lookup"><span data-stu-id="06368-106">The following illustration depicts a trusted subsystem process.</span></span>  
  
 <span data-ttu-id="06368-107">![Trusted subsystem](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span><span class="sxs-lookup"><span data-stu-id="06368-107">![Trusted subsystem](../../../../docs/framework/wcf/feature-details/media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")</span></span>  
  
 <span data-ttu-id="06368-108">Die folgenden Schritte beschreiben den vertrauenswürdigen Subsystemprozess:</span><span class="sxs-lookup"><span data-stu-id="06368-108">The following steps describe the trusted subsystem process as illustrated:</span></span>  
  
1. <span data-ttu-id="06368-109">Der Client reicht zusammen mit Anmeldeinformationen eine Anforderung beim vertrauenswürdigen Subsystem ein.</span><span class="sxs-lookup"><span data-stu-id="06368-109">The client submits a request to the trusted subsystem, along with credentials.</span></span>  
  
2. <span data-ttu-id="06368-110">Das vertrauenswürdige Subsystem wird authentifiziert und autorisiert den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="06368-110">The trusted subsystem authenticates and authorizes the user.</span></span>  
  
3. <span data-ttu-id="06368-111">Das vertrauenswürdige Subsystem sendet eine Anforderungsnachricht an die Remoteressource.</span><span class="sxs-lookup"><span data-stu-id="06368-111">The trusted subsystem sends a request message to the remote resource.</span></span> <span data-ttu-id="06368-112">Diese Anforderung wird von Anmeldeinformationen für das vertrauenswürdige Subsystem (oder das Dienstkonto, unter dem der vertrauenswürdige Subsystemprozess durchgeführt wird) begleitet.</span><span class="sxs-lookup"><span data-stu-id="06368-112">This request is accompanied by the credentials for the trusted subsystem (or the service account under which the trusted subsystem process is being executed).</span></span>  
  
4. <span data-ttu-id="06368-113">Die Back-End-Ressource authentifiziert und autorisiert das vertrauenswürdige Subsystem.</span><span class="sxs-lookup"><span data-stu-id="06368-113">The back-end resource authenticates and authorizes the trusted subsystem.</span></span> <span data-ttu-id="06368-114">Es verarbeitet dann die Anforderung und gibt eine Antwort zum vertrauenswürdigen Subsystem aus.</span><span class="sxs-lookup"><span data-stu-id="06368-114">It then processes the request and issues a response to the trusted subsystem.</span></span>  
  
5. <span data-ttu-id="06368-115">Das vertrauenswürdige Subsystem verarbeitet die Antwort und gibt seine eigene Antwort an den Client heraus.</span><span class="sxs-lookup"><span data-stu-id="06368-115">The trusted subsystem processes the response and issues its own response to the client.</span></span>  
  
|<span data-ttu-id="06368-116">Merkmal</span><span class="sxs-lookup"><span data-stu-id="06368-116">Characteristic</span></span>|<span data-ttu-id="06368-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06368-117">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="06368-118">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="06368-118">Security Mode</span></span>|<span data-ttu-id="06368-119">Meldung</span><span class="sxs-lookup"><span data-stu-id="06368-119">Message</span></span>|  
|<span data-ttu-id="06368-120">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="06368-120">Interoperability</span></span>|<span data-ttu-id="06368-121">Windows Communication Foundation (WCF) nur.</span><span class="sxs-lookup"><span data-stu-id="06368-121">Windows Communication Foundation (WCF) only.</span></span>|  
|<span data-ttu-id="06368-122">Authentifizierung (Dienst)</span><span class="sxs-lookup"><span data-stu-id="06368-122">Authentication (service)</span></span>|<span data-ttu-id="06368-123">Sicherheitstokendienst authentifiziert und autorisiert Clients.</span><span class="sxs-lookup"><span data-stu-id="06368-123">Security token service authenticates and authorizes clients.</span></span>|  
|<span data-ttu-id="06368-124">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="06368-124">Authentication (client)</span></span>|<span data-ttu-id="06368-125">Das vertrauenswürdige Subsystem authentifiziert den Client, und die Ressource authentifiziert den vertrauenswürdigen Subsystemdienst.</span><span class="sxs-lookup"><span data-stu-id="06368-125">The trusted subsystem authenticates the client and the resource authenticates the trusted subsystem service.</span></span>|  
|<span data-ttu-id="06368-126">Integrität</span><span class="sxs-lookup"><span data-stu-id="06368-126">Integrity</span></span>|<span data-ttu-id="06368-127">Ja</span><span class="sxs-lookup"><span data-stu-id="06368-127">Yes</span></span>|  
|<span data-ttu-id="06368-128">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="06368-128">Confidentiality</span></span>|<span data-ttu-id="06368-129">Ja</span><span class="sxs-lookup"><span data-stu-id="06368-129">Yes</span></span>|  
|<span data-ttu-id="06368-130">Transport</span><span class="sxs-lookup"><span data-stu-id="06368-130">Transport</span></span>|<span data-ttu-id="06368-131">HTTP zwischen Client und dem vertrauenswürdigen Subsystemdienst.</span><span class="sxs-lookup"><span data-stu-id="06368-131">HTTP between client and the trusted subsystem service.</span></span><br /><br /> <span data-ttu-id="06368-132">NET.TCP zwischen dem vertrauenswürdigen Subsystemdienst und der Ressource (Back-End-Dienst).</span><span class="sxs-lookup"><span data-stu-id="06368-132">NET.TCP between trusted subsystem service and the resource (back-end service).</span></span>|  
|<span data-ttu-id="06368-133">Bindung</span><span class="sxs-lookup"><span data-stu-id="06368-133">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding> <span data-ttu-id="06368-134">and <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="06368-134">and <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)</span></span>|  
  
## <a name="resource-back-end-service"></a><span data-ttu-id="06368-135">Ressource (Back-End-Dienst)</span><span class="sxs-lookup"><span data-stu-id="06368-135">Resource (Back-End Service)</span></span>  
  
### <a name="code"></a><span data-ttu-id="06368-136">Code</span><span class="sxs-lookup"><span data-stu-id="06368-136">Code</span></span>  
 <span data-ttu-id="06368-137">Im folgenden Code wird veranschaulicht, wie ein Dienstendpunkt für die Ressource erstellt wird, der Transportsicherheit über das TCP-Transportprotokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="06368-137">The following code shows how to create a service endpoint for the resource, which uses transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystemsResource#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsresource/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsResource#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsresource/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="06368-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="06368-138">Configuration</span></span>  
 <span data-ttu-id="06368-139">Mit der folgenden Konfiguration wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="06368-139">The following configuration sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.BackendService"  
               behaviorConfiguration="BackendServiceBehavior">  
        <endpoint address="net.tcp://localhost.com:8001/BackendService"  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="BackendServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, BackendService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="trusted-subsystem"></a><span data-ttu-id="06368-140">Vertrauenswürdiges Subsystem</span><span class="sxs-lookup"><span data-stu-id="06368-140">Trusted Subsystem</span></span>  
  
### <a name="code"></a><span data-ttu-id="06368-141">Code</span><span class="sxs-lookup"><span data-stu-id="06368-141">Code</span></span>  
 <span data-ttu-id="06368-142">Der folgende Code veranschaulicht, wie Sie einen Dienstendpunkt für das vertrauenswürdige Subsystem erstellen, der Nachrichtensicherheit über das HTTP-Protokoll und einen Benutzernamen und ein Kennwort für die Authentifizierung nutzt.</span><span class="sxs-lookup"><span data-stu-id="06368-142">The following code shows how to create a service endpoint for the trusted subsystem that uses message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystems#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#1)]
 [!code-vb[TrustedSubSystems#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#1)]  
  
 <span data-ttu-id="06368-143">Der folgende Code zeigt einen Dienst in einem vertrauenswürdigen Subsystem, der mit einem Back-End-Dienst mithilfe von Transportsicherheit über das TCP-Transportprotokoll kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="06368-143">The following code shows a service in a trusted subsystem that communicates with a back-end service using transport security over the TCP transport protocol.</span></span>  
  
 [!code-csharp[TrustedSubSystems#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#2)]
 [!code-vb[TrustedSubSystems#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="06368-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="06368-144">Configuration</span></span>  
 <span data-ttu-id="06368-145">Mit der folgenden Konfiguration wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="06368-145">The following configuration sets up the same endpoint using configuration.</span></span> <span data-ttu-id="06368-146">Beachten Sie die beiden Bindungen: Eine sichert den im vertrauenswürdigen Subsystem gehosteten Dienst aus, und die andere kommuniziert zwischen dem vertrauenswürdigen Subsystem und die Back-End-Dienst.</span><span class="sxs-lookup"><span data-stu-id="06368-146">Note the two bindings: One secures the service hosted in the trusted subsystem and the other communicates between the trusted subsystem and the back-end service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.FacadeService"  
               behaviorConfiguration="FacadeServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/FacadeService"/>  
          </baseAddresses>  
        </host>  
        <endpoint address="http://localhost:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <client>  
      <endpoint name=""   
                address="net.tcp://contoso.com:8001/BackendService"  
                binding="customBinding"  
                bindingConfiguration="ClientBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
      <customBinding>  
        <binding name="ClientBinding">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="FacadeServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                storeLocation="LocalMachine"  
                                storeName="My"  
                                x509FindType="FindBySubjectName" />  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, FacadeService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="06368-147">Client</span><span class="sxs-lookup"><span data-stu-id="06368-147">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="06368-148">Code</span><span class="sxs-lookup"><span data-stu-id="06368-148">Code</span></span>  
 <span data-ttu-id="06368-149">Der folgende Code veranschaulicht, wie Sie einen Client, der mit dem vertrauenswürdigen Subsystem kommuniziert, mithilfe von Nachrichtensicherheit über das HTTP-Protokoll und Benutzernamen und Kennwort für die Authentifizierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="06368-149">The following code shows how to create the client that communicates with the trusted subsystem by using message security over the HTTP protocol and a user name and password for authentication.</span></span>  
  
 [!code-csharp[TrustedSubSystemsClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsclient/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsclient/vb/source.vb#1)]  
  
### <a name="configuration"></a><span data-ttu-id="06368-150">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="06368-150">Configuration</span></span>  
 <span data-ttu-id="06368-151">Der folgende Code konfiguriert den Client so, dass Nachrichtensicherheit über das HTTP-Protokoll und Benutzername und Kennwort für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06368-151">The following code configures the client to use message security over the HTTP protocol and a user name and password for authentication.</span></span> <span data-ttu-id="06368-152">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06368-152">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <client>  
        <endpoint name=""   
                  address="http://www.cohowinery.com:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientUserNameBehavior"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientUserNameBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06368-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06368-153">See also</span></span>

- [<span data-ttu-id="06368-154">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="06368-154">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="06368-155">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="06368-155">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
