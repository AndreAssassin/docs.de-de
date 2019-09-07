---
title: <transport> von <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 95cfa076f62f767af431ff5a0bcc2ca31b824e30
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399240"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="9604c-102">\<Transport > von \<WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9604c-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="9604c-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="9604c-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="9604c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9604c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9604c-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9604c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9604c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9604c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9604c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSHttpBinding->** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9604c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="9604c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="9604c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9604c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9604c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="9604c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**</span><span class="sxs-lookup"><span data-stu-id="9604c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9604c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="9604c-111">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="9604c-112">Typ</span><span class="sxs-lookup"><span data-stu-id="9604c-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="9604c-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9604c-113">Attributes and Elements</span></span>

<span data-ttu-id="9604c-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9604c-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9604c-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="9604c-115">Attributes</span></span>

|<span data-ttu-id="9604c-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="9604c-116">Attribute</span></span>|<span data-ttu-id="9604c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9604c-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="9604c-118">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="9604c-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9604c-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9604c-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="9604c-120">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="9604c-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9604c-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9604c-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="9604c-122">Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="9604c-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9604c-123">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9604c-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9604c-124">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="9604c-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9604c-125">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="9604c-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="9604c-126">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9604c-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="9604c-127">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9604c-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9604c-128">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="9604c-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9604c-129">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9604c-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9604c-130">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="9604c-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9604c-131">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9604c-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9604c-132">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="9604c-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="9604c-133">Wert</span><span class="sxs-lookup"><span data-stu-id="9604c-133">Value</span></span>|<span data-ttu-id="9604c-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9604c-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="9604c-135">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9604c-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="9604c-136">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="9604c-137">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="9604c-138">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="9604c-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="9604c-139">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="9604c-140">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="9604c-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9604c-141">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="9604c-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="9604c-142">Wert</span><span class="sxs-lookup"><span data-stu-id="9604c-142">Value</span></span>|<span data-ttu-id="9604c-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9604c-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="9604c-144">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9604c-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="9604c-145">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="9604c-146">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="9604c-147">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="9604c-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="9604c-148">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9604c-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="9604c-149">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="9604c-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9604c-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9604c-150">Child Elements</span></span>

<span data-ttu-id="9604c-151">Keine</span><span class="sxs-lookup"><span data-stu-id="9604c-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9604c-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9604c-152">Parent Elements</span></span>

|<span data-ttu-id="9604c-153">Element</span><span class="sxs-lookup"><span data-stu-id="9604c-153">Element</span></span>|<span data-ttu-id="9604c-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9604c-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9604c-155">\<security></span><span class="sxs-lookup"><span data-stu-id="9604c-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="9604c-156">Stellt die Sicherheitsfunktionen des [ \<WSHttpBinding->](wshttpbinding.md)dar.</span><span class="sxs-lookup"><span data-stu-id="9604c-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="9604c-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9604c-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="9604c-158">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9604c-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9604c-159">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9604c-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9604c-160">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9604c-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9604c-161">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9604c-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9604c-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="9604c-162">\<binding></span></span>](../../../misc/binding.md)
