---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 68e3a0802a10b14148188a81ee24ed901caa147f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925383"
---
# <a name="issuedtoken"></a><span data-ttu-id="2ec7c-101">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="2ec7c-101">\<issuedToken></span></span>
<span data-ttu-id="2ec7c-102">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="2ec7c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2ec7c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2ec7c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2ec7c-104">\<behaviors></span></span>  
<span data-ttu-id="2ec7c-105">endpointverhaltenbereich</span><span class="sxs-lookup"><span data-stu-id="2ec7c-105">endpointBehaviors section</span></span>  
<span data-ttu-id="2ec7c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2ec7c-106">\<behavior></span></span>  
<span data-ttu-id="2ec7c-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2ec7c-107">\<clientCredentials></span></span>  
<span data-ttu-id="2ec7c-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="2ec7c-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec7c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ec7c-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ec7c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec7c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ec7c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ec7c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2ec7c-112">Attributes</span></span>  
  
|<span data-ttu-id="2ec7c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2ec7c-113">Attribute</span></span>|<span data-ttu-id="2ec7c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec7c-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="2ec7c-115">Optionales boolesches Attribut, das angibt, ob Token zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="2ec7c-116">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="2ec7c-117">Optionales Zeichenfolgenattribut, das angibt, welche Zufallsvariablen (Entropien) für Handshakevorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="2ec7c-118">Zu den Werten zählen `ClientEntropy`, `ServerEntropy` und `CombinedEntropy`. Die Standardeinstellung lautet `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="2ec7c-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="2ec7c-120">Optionales Ganzzahlattribut, das den Prozentwert eines gültigen Zeitrahmens (geliefert vom Tokenaussteller) angibt, der verstreichen kann, bevor ein Token erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="2ec7c-121">Die Werte reichen von 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-121">Values are from 0 to 100.</span></span> <span data-ttu-id="2ec7c-122">Die Standardeinstellung ist 60, was 60 % der Zeiten ohne Aktivität entspricht, bevor ein erneuter Versuch durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="2ec7c-123">Optionales Attribut, das das für die Kommunikation mit dem Aussteller zu verwendende Kanalverhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="2ec7c-124">Optionales Attribut, das das für die Kommunikation mit dem lokalen Aussteller zu verwendende Kanalverhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="2ec7c-125">Optionales Timespan-Attribut, das die Dauer angibt, die ausgestellte Token zwischengespeichert werden, wenn der Tokenaussteller (ein STS) keine Zeit angibt.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="2ec7c-126">Der Standardwert ist "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="2ec7c-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ec7c-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec7c-127">Child Elements</span></span>  
  
|<span data-ttu-id="2ec7c-128">Element</span><span class="sxs-lookup"><span data-stu-id="2ec7c-128">Element</span></span>|<span data-ttu-id="2ec7c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec7c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec7c-130">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="2ec7c-130">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="2ec7c-131">Gibt die Adresse des lokalen Tokenausstellers sowie die Bindung an, die für die Kommunikation mit dem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="2ec7c-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="2ec7c-132">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="2ec7c-133">Gibt das Endpunktverhalten an, das beim Kontaktieren eines lokalen Ausstellers verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ec7c-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2ec7c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="2ec7c-135">Element</span><span class="sxs-lookup"><span data-stu-id="2ec7c-135">Element</span></span>|<span data-ttu-id="2ec7c-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec7c-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ec7c-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2ec7c-137">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="2ec7c-138">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec7c-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ec7c-139">Remarks</span></span>  
 <span data-ttu-id="2ec7c-140">Ein ausgestelltes Token ist ein benutzerdefinierter Anmeldeinformationstyp, zum Beispiel für die Authentifizierung mit einem Secure Token Service (STS) in einem Verbundszenario.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="2ec7c-141">Standardmäßig ist das Token ein SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="2ec7c-142">Weitere Informationen finden Sie unter Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="2ec7c-142">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="2ec7c-143">und Verbund [-und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="2ec7c-143">and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="2ec7c-144">Dieser Abschnitt enthält die Elemente, die zum Konfigurieren eines lokalen Tokenausstellers verwendet werden, bzw. die mit einem Sicherheitstokendienst verwendeten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="2ec7c-145">Anweisungen zum Konfigurieren eines Clients für die Verwendung eines lokalen Ausstellers finden [Sie unter Gewusst wie: Konfigurieren Sie einen lokalen](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)Aussteller.</span><span class="sxs-lookup"><span data-stu-id="2ec7c-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec7c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ec7c-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="2ec7c-147">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="2ec7c-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2ec7c-148">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2ec7c-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2ec7c-149">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2ec7c-149">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2ec7c-150">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="2ec7c-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2ec7c-151">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="2ec7c-151">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="2ec7c-152">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="2ec7c-152">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="2ec7c-153">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="2ec7c-153">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
