---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 07fc2c4c52c29de1cfc9f498a6dc6b6da887b502
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925344"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="bb59a-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="bb59a-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="bb59a-102">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb59a-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="bb59a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bb59a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="bb59a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bb59a-104">\<bindings></span></span>  
<span data-ttu-id="bb59a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bb59a-105">\<customBinding></span></span>  
<span data-ttu-id="bb59a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="bb59a-106">\<binding></span></span>  
<span data-ttu-id="bb59a-107">\<security></span><span class="sxs-lookup"><span data-stu-id="bb59a-107">\<security></span></span>  
<span data-ttu-id="bb59a-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="bb59a-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb59a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb59a-109">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="bb59a-110">Typ</span><span class="sxs-lookup"><span data-stu-id="bb59a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb59a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb59a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bb59a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb59a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb59a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb59a-113">Attributes</span></span>  
  
|<span data-ttu-id="bb59a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="bb59a-114">Attribute</span></span>|<span data-ttu-id="bb59a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb59a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb59a-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="bb59a-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="bb59a-117">Gibt die Versionen der Sicherheitsspezifikationen (WS-Security, WS-Trust, WS-Secure Conversation und WS-Security Policy) an, die von der Bindung unterstützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb59a-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="bb59a-118">Dieser Wert ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="bb59a-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="bb59a-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="bb59a-119">inclusionMode</span></span>|<span data-ttu-id="bb59a-120">Gibt die Tokeneinschlussanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="bb59a-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="bb59a-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="bb59a-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="bb59a-122">keySize</span><span class="sxs-lookup"><span data-stu-id="bb59a-122">keySize</span></span>|<span data-ttu-id="bb59a-123">Eine ganze Zahl, die die Größe des Tokenschlüssels angibt.</span><span class="sxs-lookup"><span data-stu-id="bb59a-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="bb59a-124">Der Standardwert ist 256.</span><span class="sxs-lookup"><span data-stu-id="bb59a-124">The default value is 256.</span></span>|  
|<span data-ttu-id="bb59a-125">keyType</span><span class="sxs-lookup"><span data-stu-id="bb59a-125">keyType</span></span>|<span data-ttu-id="bb59a-126">Ein gültiger Wert von <xref:System.IdentityModel.Tokens.SecurityKeyType>, der den Schlüsseltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="bb59a-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="bb59a-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="bb59a-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="bb59a-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="bb59a-128">tokenType</span></span>|<span data-ttu-id="bb59a-129">Eine Zeichenfolge, die den Tokentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="bb59a-129">A string that specifies the token type.</span></span> <span data-ttu-id="bb59a-130">Der Standardwert ist "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="bb59a-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb59a-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb59a-131">Child Elements</span></span>  
  
|<span data-ttu-id="bb59a-132">Element</span><span class="sxs-lookup"><span data-stu-id="bb59a-132">Element</span></span>|<span data-ttu-id="bb59a-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb59a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb59a-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="bb59a-134">\<additionalRequestParameters></span></span>](additionalrequestparameters-element.md)|<span data-ttu-id="bb59a-135">Eine Auflistung von Konfigurationselementen, die zusätzliche Anforderungsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="bb59a-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="bb59a-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="bb59a-136">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="bb59a-137">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="bb59a-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="bb59a-138">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="bb59a-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="bb59a-139">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bb59a-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="bb59a-140">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="bb59a-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="bb59a-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="bb59a-141">\<issuer></span></span>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="bb59a-142">Ein Konfigurationselement, das den Endpunkt angibt, der das aktuelle Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="bb59a-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="bb59a-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="bb59a-143">\<issuerMetadata></span></span>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="bb59a-144">Ein Konfigurationselement, das die Endpunktadresse der Metadaten des Tokenausstellers angibt.</span><span class="sxs-lookup"><span data-stu-id="bb59a-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb59a-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb59a-145">Parent Elements</span></span>  
  
|<span data-ttu-id="bb59a-146">Element</span><span class="sxs-lookup"><span data-stu-id="bb59a-146">Element</span></span>|<span data-ttu-id="bb59a-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb59a-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb59a-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="bb59a-148">\<secureConversationBootstrap></span></span>](secureconversationbootstrap.md)|<span data-ttu-id="bb59a-149">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb59a-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="bb59a-150">\<security></span><span class="sxs-lookup"><span data-stu-id="bb59a-150">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="bb59a-151">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="bb59a-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb59a-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb59a-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bb59a-153">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bb59a-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bb59a-154">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="bb59a-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bb59a-155">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="bb59a-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bb59a-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bb59a-156">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="bb59a-157">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="bb59a-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="bb59a-158">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bb59a-158">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="bb59a-159">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb59a-159">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="bb59a-160">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bb59a-160">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="bb59a-161">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="bb59a-161">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="bb59a-162">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bb59a-162">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
