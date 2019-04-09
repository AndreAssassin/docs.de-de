---
title: COR_GC_STAT_TYPES-Enumeration
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e228cfbdade420c4d5248ffd417c6131083ee74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110416"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="8f482-102">COR_GC_STAT_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8f482-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="8f482-103">Gibt an, die Statistiken für eine Garbagecollection aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="8f482-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f482-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f482-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="8f482-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f482-105">Remarks</span></span>  
 <span data-ttu-id="8f482-106">Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) sind, dass die Struktur festgelegt werden, indem [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8f482-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="8f482-107">Member</span><span class="sxs-lookup"><span data-stu-id="8f482-107">Members</span></span>  
  
|<span data-ttu-id="8f482-108">Member</span><span class="sxs-lookup"><span data-stu-id="8f482-108">Member</span></span>|<span data-ttu-id="8f482-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f482-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="8f482-110">Datensätze werden die Anzahl der Garbage Collections für jede Generierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8f482-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="8f482-111">Datensätze speicherauslastung und Garbage Collection Größe speicherstatistiken.</span><span class="sxs-lookup"><span data-stu-id="8f482-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f482-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f482-112">Requirements</span></span>  
 <span data-ttu-id="8f482-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f482-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f482-114">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="8f482-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 **<span data-ttu-id="8f482-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8f482-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f482-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f482-116">See also</span></span>

- [<span data-ttu-id="8f482-117">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="8f482-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="8f482-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8f482-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
