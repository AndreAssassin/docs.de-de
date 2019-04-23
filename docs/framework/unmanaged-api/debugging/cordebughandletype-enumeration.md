---
title: CorDebugHandleType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220460"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="0e2a5-102">CorDebugHandleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0e2a5-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="0e2a5-103">Gibt den Handletyp an.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e2a5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="0e2a5-105">Member</span><span class="sxs-lookup"><span data-stu-id="0e2a5-105">Members</span></span>  
  
|<span data-ttu-id="0e2a5-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e2a5-106">Member</span></span>|<span data-ttu-id="0e2a5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e2a5-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="0e2a5-108">Das Handle ist stark, dadurch wird verhindert, dass ein Objekt durch die Garbagecollection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="0e2a5-109">Das Handle ist schwach ist, die ein Objekt verhindert nicht, dass durch die Garbagecollection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="0e2a5-110">Das Handle wird ungültig, wenn das Objekt gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e2a5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e2a5-111">Requirements</span></span>  
 <span data-ttu-id="0e2a5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e2a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e2a5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e2a5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e2a5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e2a5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e2a5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e2a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2a5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e2a5-116">See also</span></span>

- [<span data-ttu-id="0e2a5-117">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0e2a5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
