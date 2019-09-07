---
title: <message> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: bce80d96b1bcec0d580f2de3fe88d5fd6ad0a3b5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400261"
---
# <a name="message-of-basichttpbinding"></a><span data-ttu-id="a7014-102">\<Nachrichten > von \<BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a7014-102">\<message> of \<basicHttpBinding></span></span>
<span data-ttu-id="a7014-103">Definiert die Einstellungen für die [ \<Sicherheit auf Nachrichten Ebene des BasicHttpBinding->](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a7014-103">Defines the settings for message-level security of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="a7014-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a7014-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a7014-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a7014-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a7014-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a7014-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a7014-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BasicHttpBinding->** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a7014-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="a7014-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="a7014-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a7014-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a7014-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="a7014-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Message >**</span><span class="sxs-lookup"><span data-stu-id="a7014-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7014-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7014-111">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7014-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7014-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a7014-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7014-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7014-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7014-114">Attributes</span></span>  
  
|<span data-ttu-id="a7014-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a7014-115">Attribute</span></span>|<span data-ttu-id="a7014-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7014-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7014-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a7014-117">algorithmSuite</span></span>|<span data-ttu-id="a7014-118">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="a7014-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="a7014-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an.</span><span class="sxs-lookup"><span data-stu-id="a7014-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="a7014-120">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="a7014-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="a7014-121">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="a7014-121">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="a7014-122">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="a7014-122">clientCredentialType</span></span>|<span data-ttu-id="a7014-123">Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-123">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="a7014-124">Die Standardeinstellung ist `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a7014-124">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="a7014-125">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="a7014-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="a7014-126">Wert</span><span class="sxs-lookup"><span data-stu-id="a7014-126">Value</span></span>|<span data-ttu-id="a7014-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7014-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7014-128">UserName</span><span class="sxs-lookup"><span data-stu-id="a7014-128">UserName</span></span>|<span data-ttu-id="a7014-129">: Erfordert, dass der Client mit Benutzernamen-Anmelde Informationen auf dem Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a7014-129">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="a7014-130">Diese Anmelde Informationen müssen mithilfe des [ \<clientCredential->](clientcredentials.md)angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-130">This credential needs to be specified using the [\<clientCredentials>](clientcredentials.md).</span></span><br /><span data-ttu-id="a7014-131">-WCF unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mit Kenn Wörtern und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="a7014-131">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="a7014-132">Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-132">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="a7014-133">Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL-Kanals.</span><span class="sxs-lookup"><span data-stu-id="a7014-133">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="a7014-134">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="a7014-134">Certificate</span></span>|<span data-ttu-id="a7014-135">Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a7014-135">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="a7014-136">Die Client [ \<Anmelde](clientcredentials.md) Informationen müssen in diesem Fall mithilfe der clientCredential-> und des [ \<ClientCertificate->](clientcertificate-of-servicecredentials.md)angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-136">The client credential in this case needs to be specified using [\<clientCredentials>](clientcredentials.md) and the [\<clientCertificate>](clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="a7014-137">Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-137">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="a7014-138">Die Dienst Anmelde Informationen müssen in diesem Fall mithilfe <xref:System.ServiceModel.Description.ClientCredentials> der-Klasse oder `ClientCredentials` dem Behavior-Element angegeben werden und das Dienst Zertifikat mithilfe des [ \<serviceCertificate->](servicecertificate-of-servicecredentials.md)angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7014-138">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7014-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7014-139">Child Elements</span></span>  
 <span data-ttu-id="a7014-140">None</span><span class="sxs-lookup"><span data-stu-id="a7014-140">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7014-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7014-141">Parent Elements</span></span>  
  
|<span data-ttu-id="a7014-142">Element</span><span class="sxs-lookup"><span data-stu-id="a7014-142">Element</span></span>|<span data-ttu-id="a7014-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7014-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7014-144">\<security></span><span class="sxs-lookup"><span data-stu-id="a7014-144">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="a7014-145">Definiert die Sicherheitsfunktionen für die [ \<BasicHttpBinding->](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a7014-145">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7014-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7014-146">Example</span></span>  
 <span data-ttu-id="a7014-147">In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7014-147">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="a7014-148">Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="a7014-148">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="a7014-149">Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`-Abschnitt der Konfigurationsdatei im `serviceCredentials`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a7014-149">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="a7014-150">Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`-Abschnitt im `clientCertificate`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a7014-150">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="a7014-151">Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="a7014-151">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
    <!-- This configuration defines the SecurityMode as Message and
         the clientCredentialType as Certificate. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
               is in the user's Trusted People store, then it will be trusted without performing a
               validation of the certificate's issuer chain. This setting is used here for convenience so that the
               sample can be run without having to have certificates issued by a certification authority (CA).
               This setting is less secure than the default, ChainTrust. The security implications of this
               setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="a7014-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7014-152">See also</span></span>

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [<span data-ttu-id="a7014-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a7014-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a7014-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a7014-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a7014-155">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a7014-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a7014-156">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a7014-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a7014-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="a7014-157">\<binding></span></span>](../../../misc/binding.md)
