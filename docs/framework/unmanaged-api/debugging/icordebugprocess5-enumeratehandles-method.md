---
title: ICorDebugProcess5::EnumerateHandles-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3cc158c48e8bb9f833429bbddaa74ed459f1b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108827"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="ec0f3-102">ICorDebugProcess5::EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="ec0f3-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="ec0f3-103">Ruft einen Enumerator für die Objekt-Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec0f3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec0f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec0f3-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="ec0f3-106">[in] Eine bitweise Kombination von [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Werte, der angibt, den Typ des Handles in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="ec0f3-107">[out] Ein Zeiger auf die Adresse einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , einen Enumerator für die Objekte, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec0f3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec0f3-108">Remarks</span></span>  
 <span data-ttu-id="ec0f3-109">`EnumerateHandles` ist eine Hilfsfunktion, die Überprüfung der Handletabelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="ec0f3-110">Es ähnelt der [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode, außer dass statt Auffüllen einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) Auflistung mit allen Objekten, das speicherbereinigt werden soll es enthält nur Objekte, die Handles aus der Handletabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="ec0f3-111">Die `types` Parameter gibt die Typen von Handles in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="ec0f3-112">`types` die folgenden drei Elemente von möglich die [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Enumeration:</span><span class="sxs-lookup"><span data-stu-id="ec0f3-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="ec0f3-113">`CorHandleStrongOnly` (Handles auf zuverlässige Verweise nur).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="ec0f3-114">`CorHandleWeakOnly` (um nur schwache Verweise Handles).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="ec0f3-115">`CorHandleAll` (alle Handles).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec0f3-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec0f3-116">Requirements</span></span>  
 <span data-ttu-id="ec0f3-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec0f3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0f3-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec0f3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec0f3-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec0f3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec0f3-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0f3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0f3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec0f3-121">See also</span></span>

- [<span data-ttu-id="ec0f3-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ec0f3-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ec0f3-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ec0f3-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
