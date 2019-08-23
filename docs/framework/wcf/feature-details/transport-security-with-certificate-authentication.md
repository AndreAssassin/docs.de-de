---
title: Transportsicherheit mit Zertifikatauthentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: f94be530fb680320813a93e256e8e411234f2e40
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968647"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="9e49f-102">Transportsicherheit mit Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="9e49f-102">Transport Security with Certificate Authentication</span></span>
<span data-ttu-id="9e49f-103">In diesem Thema wird die Server- und Clientauthentifizierung mit X.509-Zertifikaten bei Verwendung der Transportsicherheit behandelt.</span><span class="sxs-lookup"><span data-stu-id="9e49f-103">This topic discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="9e49f-104">Weitere Informationen zu X.509-Zertifikaten finden Sie unter [X.509 Public Key Certificates (X.509-Zertifikate mit öffentlichem Schlüssel)](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span><span class="sxs-lookup"><span data-stu-id="9e49f-104">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="9e49f-105">Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter von Zertifikaten handelt.</span><span class="sxs-lookup"><span data-stu-id="9e49f-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="9e49f-106">In einer Windows Server-Domäne können Sie Active Directory-Zertifikatdienste verwenden, um Zertifikate für Clientcomputer in der Domäne auszustellen.</span><span class="sxs-lookup"><span data-stu-id="9e49f-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="9e49f-107">Weitere Informationen finden Sie unter [Windows 2008 R2-Zertifikat Dienste](https://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="9e49f-107">For more information see [Windows 2008 R2 Certificate Services](https://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span></span> <span data-ttu-id="9e49f-108">In diesem Szenario wird der Dienst unter Internetinformationsdienste (IIS) konfiguriert mit Secure Sockets Layer (SSL) gehostet.</span><span class="sxs-lookup"><span data-stu-id="9e49f-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="9e49f-109">Der Dienst ist mit einem SSL-Zertifikat (X.509) konfiguriert, um Clients das Überprüfen der Identität des Servers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9e49f-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="9e49f-110">Der Client ist ebenfalls mit einem X.509-Zertifikat konfiguriert, das es dem Dienst ermöglicht, die Identität des Clients zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9e49f-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="9e49f-111">Das Zertifikat des Servers muss für den Client vertrauenswürdig sein und das Zertifikat des Clients für den Server.</span><span class="sxs-lookup"><span data-stu-id="9e49f-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="9e49f-112">Die eigentlichen Mechanismen, anhand derer der Dienst und der Client die Identität des anderen überprüfen, werden in diesem Thema nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="9e49f-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this topic.</span></span> <span data-ttu-id="9e49f-113">Weitere Informationen finden Sie [unter digitale Signatur auf Wikipedia](https://go.microsoft.com/fwlink/?LinkId=253157).</span><span class="sxs-lookup"><span data-stu-id="9e49f-113">For more information see [Digital Signature on Wikipedia](https://go.microsoft.com/fwlink/?LinkId=253157).</span></span>  
  
 <span data-ttu-id="9e49f-114">In diesem Szenario wird das im folgenden Diagramm dargestellte Anforderungs-/Antwortnachrichtenmuster implementiert.</span><span class="sxs-lookup"><span data-stu-id="9e49f-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="9e49f-115">![Sichere Übertragung mit Zertifikaten](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8F 7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="9e49f-115">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="9e49f-116">Weitere Informationen zum Verwenden eines Zertifikats mit einem Dienst finden Sie unter [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) und [Gewusst wie: Konfigurieren Sie einen Port mit einem SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="9e49f-116">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="9e49f-117">In der folgenden Tabelle werden die verschiedenen Merkmale des Szenarios beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e49f-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="9e49f-118">Merkmal</span><span class="sxs-lookup"><span data-stu-id="9e49f-118">Characteristic</span></span>|<span data-ttu-id="9e49f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e49f-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9e49f-120">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="9e49f-120">Security Mode</span></span>|<span data-ttu-id="9e49f-121">Transport</span><span class="sxs-lookup"><span data-stu-id="9e49f-121">Transport</span></span>|  
|<span data-ttu-id="9e49f-122">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9e49f-122">Interoperability</span></span>|<span data-ttu-id="9e49f-123">Mit vorhandenen Webdienstclients und Diensten.</span><span class="sxs-lookup"><span data-stu-id="9e49f-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="9e49f-124">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="9e49f-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="9e49f-125">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="9e49f-125">Authentication (Client)</span></span>|<span data-ttu-id="9e49f-126">Ja (mit einem SSL-Zertifikat)</span><span class="sxs-lookup"><span data-stu-id="9e49f-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="9e49f-127">Ja (mit einem X.509-Zertifikat)</span><span class="sxs-lookup"><span data-stu-id="9e49f-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="9e49f-128">Datenintegrität</span><span class="sxs-lookup"><span data-stu-id="9e49f-128">Data Integrity</span></span>|<span data-ttu-id="9e49f-129">Ja</span><span class="sxs-lookup"><span data-stu-id="9e49f-129">Yes</span></span>|  
|<span data-ttu-id="9e49f-130">Datenvertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="9e49f-130">Data Confidentiality</span></span>|<span data-ttu-id="9e49f-131">Ja</span><span class="sxs-lookup"><span data-stu-id="9e49f-131">Yes</span></span>|  
|<span data-ttu-id="9e49f-132">Transport</span><span class="sxs-lookup"><span data-stu-id="9e49f-132">Transport</span></span>|<span data-ttu-id="9e49f-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="9e49f-133">HTTPS</span></span>|  
|<span data-ttu-id="9e49f-134">Bindung</span><span class="sxs-lookup"><span data-stu-id="9e49f-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="9e49f-135">Konfigurieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="9e49f-135">Configure the Service</span></span>  
 <span data-ttu-id="9e49f-136">Da der Dienst in diesem Szenario unter IIS gehostet wird, wird er mit einer Datei "web.config" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9e49f-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="9e49f-137">Die folgende Datei "web.config" zeigt, wie die <xref:System.ServiceModel.WSHttpBinding> zur Verwendung von Transportsicherheit und X.509-Clientanmeldeinformationen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="9e49f-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="9e49f-138">Konfigurieren des Clients</span><span class="sxs-lookup"><span data-stu-id="9e49f-138">Configure the Client</span></span>  
 <span data-ttu-id="9e49f-139">Der Client kann im Code oder in einer Datei "app.config" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9e49f-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="9e49f-140">Das folgende Beispiel zeigt, wie Sie den Client im Code konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e49f-140">The following example shows how to configure the client in code.</span></span>  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="9e49f-141">Alternativ können Sie den Client wie im folgenden Beispiel dargestellt in einer Datei "app.config" konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="9e49f-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e49f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e49f-142">See also</span></span>

- [<span data-ttu-id="9e49f-143">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9e49f-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="9e49f-144">Sicherheitsmodell für Windows Server-App-Fabric</span><span class="sxs-lookup"><span data-stu-id="9e49f-144">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
