---
title: Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
ms.openlocfilehash: 93136d4c87463db7128a68957b243c1ef13a90eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174056"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="df081-102">Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität</span><span class="sxs-lookup"><span data-stu-id="df081-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>
<span data-ttu-id="df081-103">Um sicherzustellen, dass die aktuellsten Inhalte an die Clientanwendung zurückgegeben werden, führt die Interaktion der Cacherichtlinie für Clients und den Anforderungen der Serverüberprüfung immer zur konservativsten Cacherichtlinie.</span><span class="sxs-lookup"><span data-stu-id="df081-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="df081-104">Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert wird und am 4. Januar abläuft.</span><span class="sxs-lookup"><span data-stu-id="df081-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="df081-105">Die folgenden Beispiele veranschaulichen die Cacherichtlinie, die von der Wechselwirkung aus dem maximalen Alter (`maxAge`) und der minimalen Aktualität (`minFresh`) der Werte entsteht.</span><span class="sxs-lookup"><span data-stu-id="df081-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
-   <span data-ttu-id="df081-106">Wenn die Cacherichtlinie `maxAge` = 2 Tage festlegt und `minFresh` nicht angegeben ist, wird der Inhalt am 3. Januar erneut überprüft.</span><span class="sxs-lookup"><span data-stu-id="df081-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="df081-107">Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 1 Tag festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell.</span><span class="sxs-lookup"><span data-stu-id="df081-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="df081-108">Entsprechend dem `minFresh`, ist der Inhalt bis zum 3. Januar aktuell.</span><span class="sxs-lookup"><span data-stu-id="df081-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="df081-109">Aus diesem Grund muss der Inhalt am 3. Januar erneut überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="df081-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="df081-110">Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 2 Tage festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell.</span><span class="sxs-lookup"><span data-stu-id="df081-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="df081-111">Entsprechend dem `minFresh`, ist der Inhalt bis zum 2. Januar aktuell.</span><span class="sxs-lookup"><span data-stu-id="df081-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="df081-112">Aus diesem Grund muss der Inhalt am 2. Januar erneut überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="df081-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df081-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df081-113">See also</span></span>

- [<span data-ttu-id="df081-114">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="df081-114">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="df081-115">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="df081-115">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="df081-116">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="df081-116">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="df081-117">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="df081-117">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [<span data-ttu-id="df081-118">Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="df081-118">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [<span data-ttu-id="df081-119">Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung</span><span class="sxs-lookup"><span data-stu-id="df081-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
