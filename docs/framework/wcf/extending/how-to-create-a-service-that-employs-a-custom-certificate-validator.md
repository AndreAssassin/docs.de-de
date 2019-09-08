---
title: 'Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: b2407c293de7f11b90586f5a55bd759a4ea734aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795680"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="9cdbe-102">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="9cdbe-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="9cdbe-103">In diesem Thema wird gezeigt, wie Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement implementieren und wie Sie Anmeldeinformationen für Clients oder Dienste konfigurieren, um die standardmäßige Zertifikatüberprüfungslogik durch das benutzerdefinierte Zertifikats-Validierungssteuerelement zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="9cdbe-104">Wenn das X. 509-Zertifikat verwendet wird, um einen Client oder Dienst zu authentifizieren, verwendet Windows Communication Foundation (WCF) standardmäßig den Windows-Zertifikat Speicher und die kryptografieapi, um das Zertifikat zu validieren und sicherzustellen, dass es vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="9cdbe-105">Es kann vorkommen, dass die integrierten Funktionen zur Zertifikatsvalidierung nicht ausreichen und geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="9cdbe-106">WCF bietet eine einfache Möglichkeit zum Ändern der Validierungs Logik, indem es Benutzern ermöglicht wird, ein benutzerdefiniertes zertifikatvalidator hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="9cdbe-107">Wenn ein benutzerdefiniertes Zertifikats-Validierungs Steuerelement angegeben wird, verwendet WCF nicht die integrierte Zertifikats Validierungs Logik, sondern verwendet stattdessen das benutzerdefinierte Validierungs Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9cdbe-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9cdbe-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="9cdbe-109">So erstellen Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="9cdbe-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="9cdbe-110">Definieren Sie eine neue Klasse, die von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="9cdbe-111">Implementieren Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="9cdbe-112">Das Zertifikat, das überprüft werden muss, wird als Argument an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="9cdbe-113">Wenn das übergebene Zertifikat gemäß der Validierungslogik nicht gültig ist, löst diese Methode eine <xref:System.IdentityModel.Tokens.SecurityTokenValidationException> aus.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="9cdbe-114">Wenn das Zertifikat gültig ist, gibt die Methode einen Wert an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9cdbe-115">Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="9cdbe-116">So geben Sie bei der Dienstkonfiguration ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an</span><span class="sxs-lookup"><span data-stu-id="9cdbe-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="9cdbe-117">Fügen Sie [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [dem System.ServiceModel->ElementeinVerhalten>ElementundeinServiceVerhaltens>hinzu.\<](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../../configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9cdbe-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="9cdbe-118">Fügen Sie ein [ \<> Verhalten](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) hinzu, `name` und legen Sie das-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="9cdbe-119">Fügen Sie dem`<behavior>` -Element eine [ \<servicecreden->](../../configure-apps/file-schema/wcf/servicecredentials.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="9cdbe-120">Fügen Sie dem `<clientCertificate>`-Element ein `<serviceCredentials>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="9cdbe-121">Fügen Sie dem`<clientCertificate>` -Element einen [ \<Authentifizierungs >](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="9cdbe-122">Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="9cdbe-123">Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="9cdbe-124">Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="9cdbe-125">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie die Konfiguration auf dem Client verwenden</span><span class="sxs-lookup"><span data-stu-id="9cdbe-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="9cdbe-126">Fügen Sie [ \<](../../configure-apps/file-schema/wcf/behaviors.md) [dem System.ServiceModel->ElementeinVerhalten>ElementundeinServiceVerhaltens>hinzu.\<](../../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../../configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9cdbe-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="9cdbe-127">Fügen Sie ein [ \<endpointverhaltensweisen->](../../configure-apps/file-schema/wcf/endpointbehaviors.md) Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="9cdbe-128">Fügen Sie ein `<behavior>`name-Element hinzu, und legen Sie das`name`-Attribut auf einen passenden Wert fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="9cdbe-129">Fügen Sie ein [ \<Clientanmelde](../../configure-apps/file-schema/wcf/clientcredentials.md) Informationen-> Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="9cdbe-130">Fügen Sie ein [ \<serviceCertificate->](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="9cdbe-131">Fügen Sie wie im folgenden Beispiel gezeigt einen [ \<Authentifizierungs >](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="9cdbe-132">Legen Sie das `customCertificateValidatorType`-Attribut auf den Validierungssteuerelementtyp fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="9cdbe-133">Legen Sie das `certificateValidationMode`-Attribut auf `Custom` fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="9cdbe-134">Im folgenden Beispiel wird das Attribut auf den Namespace und den Namen des Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="9cdbe-135">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Dienstseite verwenden</span><span class="sxs-lookup"><span data-stu-id="9cdbe-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="9cdbe-136">Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="9cdbe-137">Sie können auf die Dienstanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="9cdbe-138">Legen Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> -Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="9cdbe-139">So geben Sie ein benutzerdefiniertes Zertifikats-Validierungssteuerelement an, indem Sie Code auf der Clientseite verwenden</span><span class="sxs-lookup"><span data-stu-id="9cdbe-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="9cdbe-140">Geben Sie das benutzerdefinierte Zertifikats-Validierungssteuerelement über die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="9cdbe-141">Sie können auf die Clientanmeldeinformationen mit der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="9cdbe-142">(Die vom [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generierte Client Klasse wird immer von der <xref:System.ServiceModel.ClientBase%601> -Klasse abgeleitet.)</span><span class="sxs-lookup"><span data-stu-id="9cdbe-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="9cdbe-143">Legen Sie die <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> -Eigenschaft auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>fest.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cdbe-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cdbe-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9cdbe-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cdbe-145">Description</span></span>  
 <span data-ttu-id="9cdbe-146">Das folgende Beispiel zeigt eine Implementierung eines benutzerdefinierten Zertifikats-Validierungssteuerelements und seine Verwendung für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="9cdbe-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9cdbe-147">Code</span><span class="sxs-lookup"><span data-stu-id="9cdbe-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9cdbe-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cdbe-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
