---
title: <security> von <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399868"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="07715-102">\<security> of \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="07715-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="07715-103">Definiert die Transportsicherheitseinstellungen für den Message Queuing (MSMQ)-Integrationskanal.</span><span class="sxs-lookup"><span data-stu-id="07715-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="07715-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07715-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07715-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="07715-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="07715-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="07715-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="07715-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MsmqIntegrationBinding->** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="07715-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="07715-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="07715-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="07715-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="07715-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07715-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="07715-110">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07715-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07715-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07715-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07715-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07715-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="07715-113">Attributes</span></span>  
  
|<span data-ttu-id="07715-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="07715-114">Attribute</span></span>|<span data-ttu-id="07715-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07715-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07715-116">Modus</span><span class="sxs-lookup"><span data-stu-id="07715-116">mode</span></span>|<span data-ttu-id="07715-117">Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung mit dem Message Queuing-Integrationskanal steuert.</span><span class="sxs-lookup"><span data-stu-id="07715-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="07715-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="07715-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="07715-119">Gar Dadurch wird die Sicherheit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="07715-119">-   None: This disables security.</span></span><br /><span data-ttu-id="07715-120">Personen Schutz und Authentifizierung werden vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="07715-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="07715-121">Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern.</span><span class="sxs-lookup"><span data-stu-id="07715-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="07715-122">Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager.</span><span class="sxs-lookup"><span data-stu-id="07715-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="07715-123">Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="07715-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="07715-124">Der Standardwert ist `Transport`.</span><span class="sxs-lookup"><span data-stu-id="07715-124">The default value is `Transport`.</span></span> <span data-ttu-id="07715-125">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="07715-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07715-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07715-126">Child Elements</span></span>  
  
|<span data-ttu-id="07715-127">Element</span><span class="sxs-lookup"><span data-stu-id="07715-127">Element</span></span>|<span data-ttu-id="07715-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07715-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07715-129">\<transport></span><span class="sxs-lookup"><span data-stu-id="07715-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="07715-130">Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.</span><span class="sxs-lookup"><span data-stu-id="07715-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="07715-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="07715-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07715-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07715-132">Parent Elements</span></span>  
  
|<span data-ttu-id="07715-133">Element</span><span class="sxs-lookup"><span data-stu-id="07715-133">Element</span></span>|<span data-ttu-id="07715-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07715-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07715-135">\<binding></span><span class="sxs-lookup"><span data-stu-id="07715-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="07715-136">Das Bindungs Element der [ \<MsmqIntegrationBinding->](msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="07715-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07715-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07715-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="07715-138">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="07715-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="07715-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="07715-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="07715-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="07715-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="07715-141">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="07715-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="07715-142">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="07715-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="07715-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="07715-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="07715-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="07715-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
