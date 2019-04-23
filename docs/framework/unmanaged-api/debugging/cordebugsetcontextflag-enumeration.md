---
title: CorDebugSetContextFlag-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5754968511f7b2db48f60b99748f10f5d27e8d21
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115686"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="50779-102">CorDebugSetContextFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="50779-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="50779-103">Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="50779-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50779-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50779-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="50779-105">Member</span><span class="sxs-lookup"><span data-stu-id="50779-105">Members</span></span>  
  
|<span data-ttu-id="50779-106">Member</span><span class="sxs-lookup"><span data-stu-id="50779-106">Member</span></span>|<span data-ttu-id="50779-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50779-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="50779-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="50779-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="50779-109">Der Kontext ist aktiven Kontext des Threads.</span><span class="sxs-lookup"><span data-stu-id="50779-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="50779-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="50779-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="50779-111">Der Kontext wurde durch das Entladen aus einem anderen Frame berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="50779-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50779-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50779-112">Remarks</span></span>  
 <span data-ttu-id="50779-113">`CorDebugSetContextFlag` enthält Werte, mit denen, die [ICorDebugStackWalk:: SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="50779-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50779-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50779-114">Requirements</span></span>  
 <span data-ttu-id="50779-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50779-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50779-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50779-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50779-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50779-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50779-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50779-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50779-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50779-119">See also</span></span>

- [<span data-ttu-id="50779-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="50779-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="50779-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="50779-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
