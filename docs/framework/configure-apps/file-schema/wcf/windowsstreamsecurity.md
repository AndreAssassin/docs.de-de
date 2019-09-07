---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: cddd9f0c1dda982c1795500723c21546bd58c92b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399095"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="ed4c3-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="ed4c3-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="ed4c3-102">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="ed4c3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ed4c3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ed4c3-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ed4c3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ed4c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ed4c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ed4c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ed4c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ed4c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="ed4c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ed4c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsStreamSecurity->**</span><span class="sxs-lookup"><span data-stu-id="ed4c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4c3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed4c3-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed4c3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed4c3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ed4c3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed4c3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed4c3-112">Attributes</span></span>  
  
|<span data-ttu-id="ed4c3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ed4c3-113">Attribute</span></span>|<span data-ttu-id="ed4c3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed4c3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed4c3-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="ed4c3-115">protectionLevel</span></span>|<span data-ttu-id="ed4c3-116">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-116">Defines message-level security.</span></span> <span data-ttu-id="ed4c3-117">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="ed4c3-118">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="ed4c3-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ed4c3-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ed4c3-120">Gar Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-120">-   None: No protection.</span></span><br /><span data-ttu-id="ed4c3-121">Gebärden Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ed4c3-122">EncryptAndSign Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="ed4c3-123">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="ed4c3-124">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed4c3-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed4c3-125">Child Elements</span></span>  
 <span data-ttu-id="ed4c3-126">None</span><span class="sxs-lookup"><span data-stu-id="ed4c3-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed4c3-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed4c3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ed4c3-128">Element</span><span class="sxs-lookup"><span data-stu-id="ed4c3-128">Element</span></span>|<span data-ttu-id="ed4c3-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed4c3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed4c3-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="ed4c3-130">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ed4c3-131">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed4c3-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed4c3-132">Remarks</span></span>  
 <span data-ttu-id="ed4c3-133">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="ed4c3-134">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="ed4c3-135">Die Konfiguration dieser Transportsicherheit wird durch dieses Konfigurationselement und durch [ \<die sslStreamSecurity->](sslstreamsecurity.md)gekapselt, die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed4c3-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4c3-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed4c3-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="ed4c3-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed4c3-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ed4c3-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed4c3-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ed4c3-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed4c3-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ed4c3-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ed4c3-140">\<customBinding></span></span>](custombinding.md)
