---
title: CorDebugIntercept-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0791a59e0325668960dcfc98816920db55bcfb87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199933"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="4ff39-102">CorDebugIntercept-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4ff39-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="4ff39-103">Gibt die Codetypen an, die schrittweise abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="4ff39-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ff39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ff39-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="4ff39-105">Member</span><span class="sxs-lookup"><span data-stu-id="4ff39-105">Members</span></span>  
  
|<span data-ttu-id="4ff39-106">Member</span><span class="sxs-lookup"><span data-stu-id="4ff39-106">Member</span></span>|<span data-ttu-id="4ff39-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ff39-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="4ff39-108">Kein Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="4ff39-109">Ein Konstruktor kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="4ff39-110">Ein Ausnahmefilter kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="4ff39-111">Code, der die Einhaltung von Sicherheitsrichtlinien erzwingt, kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="4ff39-112">Eine Kontextrichtlinie kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="4ff39-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ff39-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="4ff39-114">Jeder Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ff39-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ff39-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ff39-115">Remarks</span></span>  
 <span data-ttu-id="4ff39-116">Verwenden der [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) Methode, um die Codetypen festzulegen, die abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="4ff39-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff39-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ff39-117">Requirements</span></span>  
 <span data-ttu-id="4ff39-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff39-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff39-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ff39-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ff39-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ff39-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4ff39-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4ff39-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ff39-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ff39-122">See also</span></span>

- [<span data-ttu-id="4ff39-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="4ff39-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
