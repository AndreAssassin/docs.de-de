---
title: ICorDebugFunctionBreakpoint-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f15b9f5961699f905e765426576bdf6f3416793
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141153"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="e21f7-102">ICorDebugFunctionBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e21f7-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="e21f7-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e21f7-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e21f7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e21f7-104">Methods</span></span>  
  
|<span data-ttu-id="e21f7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e21f7-105">Method</span></span>|<span data-ttu-id="e21f7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e21f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e21f7-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="e21f7-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="e21f7-108">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e21f7-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="e21f7-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e21f7-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="e21f7-110">Ruft den Offset des Haltepunkts in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="e21f7-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e21f7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e21f7-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e21f7-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e21f7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e21f7-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e21f7-113">Requirements</span></span>  
 <span data-ttu-id="e21f7-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e21f7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e21f7-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e21f7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e21f7-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e21f7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e21f7-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e21f7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e21f7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e21f7-118">See also</span></span>

- [<span data-ttu-id="e21f7-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e21f7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
