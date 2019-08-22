---
title: <clear>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658863"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="d3e30-102">\<Löschen Sie > Element \<für NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="d3e30-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="d3e30-103">Löscht alle `namedCache` Einträge in der `namedCaches` -Auflistung für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="d3e30-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="d3e30-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="d3e30-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="d3e30-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d3e30-105">\<memoryCache></span></span>  
<span data-ttu-id="d3e30-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d3e30-106">\<namedCaches></span></span>  
<span data-ttu-id="d3e30-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d3e30-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e30-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3e30-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d3e30-109">Typ</span><span class="sxs-lookup"><span data-stu-id="d3e30-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3e30-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e30-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d3e30-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3e30-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3e30-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3e30-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="d3e30-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e30-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d3e30-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3e30-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d3e30-115">Element</span><span class="sxs-lookup"><span data-stu-id="d3e30-115">Element</span></span>|<span data-ttu-id="d3e30-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3e30-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3e30-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d3e30-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d3e30-118">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="d3e30-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3e30-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3e30-119">Remarks</span></span>  
 <span data-ttu-id="d3e30-120">Das `clear` -Element löscht `namedCache` alle Einträge in der benannten Cache Auflistung für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="d3e30-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="d3e30-121">Sie können das `clear` -Element verwenden, bevor Sie `add` das-Element verwenden, um einen neuen benannten Cache Eintrag hinzuzufügen, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d3e30-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e30-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3e30-122">See also</span></span>

- [<span data-ttu-id="d3e30-123">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3e30-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
