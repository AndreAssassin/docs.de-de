---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: c410967e84c9318d21ce0b3072d08b026a37b190
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399208"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="fc2ef-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="fc2ef-101">\<useManagedPresentation></span></span>
<span data-ttu-id="fc2ef-102">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="fc2ef-103">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="fc2ef-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc2ef-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc2ef-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc2ef-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fc2ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fc2ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fc2ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="fc2ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="fc2ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="fc2ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fc2ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useManagedPresentation->**</span><span class="sxs-lookup"><span data-stu-id="fc2ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2ef-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc2ef-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc2ef-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc2ef-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fc2ef-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc2ef-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc2ef-113">Attributes</span></span>  
 <span data-ttu-id="fc2ef-114">Keine</span><span class="sxs-lookup"><span data-stu-id="fc2ef-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc2ef-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc2ef-115">Child Elements</span></span>  
 <span data-ttu-id="fc2ef-116">None</span><span class="sxs-lookup"><span data-stu-id="fc2ef-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc2ef-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc2ef-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fc2ef-118">Element</span><span class="sxs-lookup"><span data-stu-id="fc2ef-118">Element</span></span>|<span data-ttu-id="fc2ef-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc2ef-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc2ef-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="fc2ef-120">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="fc2ef-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc2ef-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc2ef-122">Remarks</span></span>  
 <span data-ttu-id="fc2ef-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="fc2ef-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="fc2ef-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2ef-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc2ef-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fc2ef-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc2ef-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fc2ef-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc2ef-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fc2ef-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc2ef-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fc2ef-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fc2ef-129">\<customBinding></span></span>](custombinding.md)
