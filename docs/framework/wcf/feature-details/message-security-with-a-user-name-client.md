---
title: Nachrichtensicherheit über einen Benutzernamenclient
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 73e984193f87b20e0e00d8ab92a7c0fd67f7968f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046567"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="005a5-102">Nachrichtensicherheit über einen Benutzernamenclient</span><span class="sxs-lookup"><span data-stu-id="005a5-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="005a5-103">Die folgende Abbildung zeigt einen Windows Communication Foundation (WCF)-Dienst und Client mit Sicherheit auf Nachrichtenebene gesichert.</span><span class="sxs-lookup"><span data-stu-id="005a5-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="005a5-104">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="005a5-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="005a5-105">Der Client wird über den Benutzernamen und das Kennwort authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="005a5-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="005a5-106">Eine beispielanwendung finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="005a5-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="005a5-107">![Nachrichtensicherheit durch Benutzernamenauthentifizierung](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="005a5-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="005a5-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="005a5-108">Characteristic</span></span>|<span data-ttu-id="005a5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="005a5-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="005a5-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="005a5-110">Security Mode</span></span>|<span data-ttu-id="005a5-111">Meldung</span><span class="sxs-lookup"><span data-stu-id="005a5-111">Message</span></span>|  
|<span data-ttu-id="005a5-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="005a5-112">Interoperability</span></span>|<span data-ttu-id="005a5-113">Windows Communication Foundation (WCF) nur</span><span class="sxs-lookup"><span data-stu-id="005a5-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="005a5-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="005a5-114">Authentication (Server)</span></span>|<span data-ttu-id="005a5-115">Für die erste Aushandlung ist eine Serverauthentifizierung erforderlich</span><span class="sxs-lookup"><span data-stu-id="005a5-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="005a5-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="005a5-116">Authentication (Client)</span></span>|<span data-ttu-id="005a5-117">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="005a5-117">User name/password</span></span>|  
|<span data-ttu-id="005a5-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="005a5-118">Integrity</span></span>|<span data-ttu-id="005a5-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="005a5-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="005a5-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="005a5-120">Confidentiality</span></span>|<span data-ttu-id="005a5-121">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="005a5-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="005a5-122">Transport</span><span class="sxs-lookup"><span data-stu-id="005a5-122">Transport</span></span>|<span data-ttu-id="005a5-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="005a5-123">HTTP</span></span>|  
|<span data-ttu-id="005a5-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="005a5-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="005a5-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="005a5-125">Service</span></span>  
 <span data-ttu-id="005a5-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="005a5-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="005a5-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="005a5-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="005a5-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="005a5-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="005a5-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="005a5-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="005a5-130">Code</span><span class="sxs-lookup"><span data-stu-id="005a5-130">Code</span></span>  
 <span data-ttu-id="005a5-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="005a5-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="005a5-132">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="005a5-132">Configuration</span></span>  
 <span data-ttu-id="005a5-133">Die folgende Konfiguration kann statt des Codes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="005a5-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="005a5-134">Client</span><span class="sxs-lookup"><span data-stu-id="005a5-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="005a5-135">Code</span><span class="sxs-lookup"><span data-stu-id="005a5-135">Code</span></span>  
 <span data-ttu-id="005a5-136">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="005a5-136">The following code creates the client.</span></span> <span data-ttu-id="005a5-137">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="005a5-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="005a5-138">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="005a5-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="005a5-139">Der Code zum Zurückgeben des Benutzernamens und des Kennworts ist hier nicht gezeigt, da dies auf Anwendungsebene erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="005a5-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="005a5-140">Verwenden Sie z. B. ein Windows Forms-Dialogfeld, um vom Benutzer Daten abzufragen.</span><span class="sxs-lookup"><span data-stu-id="005a5-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="005a5-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="005a5-141">Configuration</span></span>  
 <span data-ttu-id="005a5-142">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="005a5-142">The following code configures the client.</span></span> <span data-ttu-id="005a5-143">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="005a5-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="005a5-144">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="005a5-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="005a5-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="005a5-145">See also</span></span>

- [<span data-ttu-id="005a5-146">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="005a5-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="005a5-147">Nachrichtensicherheit – Benutzername</span><span class="sxs-lookup"><span data-stu-id="005a5-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)
- [<span data-ttu-id="005a5-148">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="005a5-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="005a5-149">\<identity></span><span class="sxs-lookup"><span data-stu-id="005a5-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
- [<span data-ttu-id="005a5-150">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="005a5-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
