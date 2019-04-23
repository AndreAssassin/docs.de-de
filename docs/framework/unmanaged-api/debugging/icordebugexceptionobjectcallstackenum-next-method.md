---
title: ICorDebugExceptionObjectCallStackEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c33f76b5eaa87c0b69497547732564921f662d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099468"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="58b16-102">ICorDebugExceptionObjectCallStackEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="58b16-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>
<span data-ttu-id="58b16-103">Ruft die angegebene Anzahl von [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen, die Informationen aus der Aufrufliste ein Exception-Objekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="58b16-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58b16-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58b16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58b16-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="58b16-106">[in] Die Anzahl der [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="58b16-106">[in] The number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="58b16-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="58b16-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="58b16-108">[out] Ein Zeiger auf die Anzahl der [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58b16-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58b16-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58b16-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b16-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58b16-110">Requirements</span></span>  
 <span data-ttu-id="58b16-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b16-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58b16-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58b16-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58b16-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58b16-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b16-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58b16-115">See also</span></span>

- [<span data-ttu-id="58b16-116">ICorDebugExceptionObjectCallStackEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58b16-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="58b16-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="58b16-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
