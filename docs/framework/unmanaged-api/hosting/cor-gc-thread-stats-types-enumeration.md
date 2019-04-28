---
title: COR_GC_THREAD_STATS_TYPES-Enumeration
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c631a0a3abb3cb2a342dfd44fdffb147b742ae3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698121"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="0c85d-102">COR_GC_THREAD_STATS_TYPES-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0c85d-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="0c85d-103">Gibt an, die Garbage Collection-Statistik für einen Thread.</span><span class="sxs-lookup"><span data-stu-id="0c85d-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c85d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c85d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="0c85d-105">Member</span><span class="sxs-lookup"><span data-stu-id="0c85d-105">Members</span></span>  
  
|<span data-ttu-id="0c85d-106">Member</span><span class="sxs-lookup"><span data-stu-id="0c85d-106">Member</span></span>|<span data-ttu-id="0c85d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c85d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="0c85d-108">Der Thread hat Bytes, die in der letzten Garbagecollection höher gestuft wurden.</span><span class="sxs-lookup"><span data-stu-id="0c85d-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c85d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c85d-109">Requirements</span></span>  
 <span data-ttu-id="0c85d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c85d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c85d-111">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="0c85d-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0c85d-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c85d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c85d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c85d-113">See also</span></span>

- [<span data-ttu-id="0c85d-114">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0c85d-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
