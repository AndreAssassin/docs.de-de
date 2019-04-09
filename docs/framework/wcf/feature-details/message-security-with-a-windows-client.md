---
title: Nachrichtensicherheit über einen Windows-Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 794a3d8e118cadd2a2752e1bbf85ef930deb2f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138644"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="b06a9-102">Nachrichtensicherheit über einen Windows-Client</span><span class="sxs-lookup"><span data-stu-id="b06a9-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="b06a9-103">Dieses Szenario zeigt einen Windows Communication Foundation (WCF)-Client und Server im nachrichtensicherheitsmodus gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="b06a9-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="b06a9-104">Client und Dienst werden mit Windows-Anmeldeinformationen authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="b06a9-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="b06a9-105">![Nachrichtensicherheit mit einem Windows-Client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="b06a9-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="b06a9-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="b06a9-106">Characteristic</span></span>|<span data-ttu-id="b06a9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b06a9-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b06a9-108">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="b06a9-108">Security Mode</span></span>|<span data-ttu-id="b06a9-109">Meldung</span><span class="sxs-lookup"><span data-stu-id="b06a9-109">Message</span></span>|  
|<span data-ttu-id="b06a9-110">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="b06a9-110">Interoperability</span></span>|<span data-ttu-id="b06a9-111">WCF Only</span><span class="sxs-lookup"><span data-stu-id="b06a9-111">WCF Only</span></span>|  
|<span data-ttu-id="b06a9-112">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="b06a9-112">Authentication (Server)</span></span>|<span data-ttu-id="b06a9-113">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="b06a9-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b06a9-114">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="b06a9-114">Authentication (Client)</span></span>|<span data-ttu-id="b06a9-115">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="b06a9-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b06a9-116">Integrität</span><span class="sxs-lookup"><span data-stu-id="b06a9-116">Integrity</span></span>|<span data-ttu-id="b06a9-117">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="b06a9-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="b06a9-118">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="b06a9-118">Confidentiality</span></span>|<span data-ttu-id="b06a9-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="b06a9-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="b06a9-120">Transport</span><span class="sxs-lookup"><span data-stu-id="b06a9-120">Transport</span></span>|<span data-ttu-id="b06a9-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="b06a9-121">NET.TCP</span></span>|  
|<span data-ttu-id="b06a9-122">Bindung</span><span class="sxs-lookup"><span data-stu-id="b06a9-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="b06a9-123">Dienst</span><span class="sxs-lookup"><span data-stu-id="b06a9-123">Service</span></span>  
 <span data-ttu-id="b06a9-124">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b06a9-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b06a9-125">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b06a9-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b06a9-126">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="b06a9-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="b06a9-127">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="b06a9-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b06a9-128">Code</span><span class="sxs-lookup"><span data-stu-id="b06a9-128">Code</span></span>  
 <span data-ttu-id="b06a9-129">Der folgende Code zeigt, wie Sie einen Dienstendpunkt erstellen, der die Nachrichtensicherheit zum Herstellen eines sicheren Kontexts mit einem Windows-Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="b06a9-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="b06a9-130">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b06a9-130">Configuration</span></span>  
 <span data-ttu-id="b06a9-131">Die folgende Konfiguration kann statt des Codes zum Einrichten des Diensts verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b06a9-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="b06a9-132">Client</span><span class="sxs-lookup"><span data-stu-id="b06a9-132">Client</span></span>  
 <span data-ttu-id="b06a9-133">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b06a9-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b06a9-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b06a9-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b06a9-135">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="b06a9-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="b06a9-136">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="b06a9-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="b06a9-137">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="b06a9-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="b06a9-138">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b06a9-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="b06a9-139">Code</span><span class="sxs-lookup"><span data-stu-id="b06a9-139">Code</span></span>  
 <span data-ttu-id="b06a9-140">Mit dem folgenden Code wird ein Client erstellt.</span><span class="sxs-lookup"><span data-stu-id="b06a9-140">The following code creates a client.</span></span> <span data-ttu-id="b06a9-141">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `Windows` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b06a9-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="b06a9-142">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b06a9-142">Configuration</span></span>  
 <span data-ttu-id="b06a9-143">Die folgende Konfiguration wird zum Festlegen der Clienteigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="b06a9-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b06a9-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b06a9-144">See also</span></span>

- [<span data-ttu-id="b06a9-145">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b06a9-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="b06a9-146">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="b06a9-146">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
