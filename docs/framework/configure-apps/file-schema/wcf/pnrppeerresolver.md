---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d7c6c8efa971fb60f0257cc1c74ceda72e31cb84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400048"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="4c67b-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="4c67b-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="4c67b-102">Gibt an, dass der PNRP (Peer Name Resolution-Protokoll)-Resolver als Resolver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c67b-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="4c67b-103">Dieses Element ist optional, da das PNRP der Standardresolver ist.</span><span class="sxs-lookup"><span data-stu-id="4c67b-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="4c67b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c67b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c67b-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4c67b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4c67b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4c67b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4c67b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4c67b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4c67b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="4c67b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4c67b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<pnrpresolver->**</span><span class="sxs-lookup"><span data-stu-id="4c67b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c67b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c67b-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c67b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c67b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4c67b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c67b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c67b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c67b-113">Attributes</span></span>  
  
|<span data-ttu-id="4c67b-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="4c67b-114">Attribute</span></span>|<span data-ttu-id="4c67b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c67b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c67b-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="4c67b-116">resolverType</span></span>|<span data-ttu-id="4c67b-117">Eine Zeichenfolge, die den zu verwendenden Resolver angibt.</span><span class="sxs-lookup"><span data-stu-id="4c67b-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="4c67b-118">Dieses Attribut ist optional.</span><span class="sxs-lookup"><span data-stu-id="4c67b-118">This attribute is optional.</span></span> <span data-ttu-id="4c67b-119">Wenn es nicht festgelegt wurde oder eine leere Zeichenfolge angegeben wurde, wird das PNRP verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c67b-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c67b-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c67b-120">Child Elements</span></span>  
 <span data-ttu-id="4c67b-121">None</span><span class="sxs-lookup"><span data-stu-id="4c67b-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c67b-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c67b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4c67b-123">Element</span><span class="sxs-lookup"><span data-stu-id="4c67b-123">Element</span></span>|<span data-ttu-id="4c67b-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c67b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c67b-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="4c67b-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4c67b-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="4c67b-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c67b-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c67b-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4c67b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c67b-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4c67b-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4c67b-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c67b-130">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="4c67b-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4c67b-131">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4c67b-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4c67b-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4c67b-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="4c67b-133">Peerresolver</span><span class="sxs-lookup"><span data-stu-id="4c67b-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
