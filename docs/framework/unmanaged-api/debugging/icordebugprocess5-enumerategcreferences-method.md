---
title: ICorDebugProcess5::EnumerateGCReferences-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 84b5da043f9bd437ee9099135ba865c1ab23bb9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129669"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="593f2-102">ICorDebugProcess5::EnumerateGCReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="593f2-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="593f2-103">Ruft einen Enumerator für alle Objekte ab, die in einem Prozess in eine Garbage Collection aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="593f2-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="593f2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="593f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="593f2-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="593f2-106">in Ein boolescher Wert, der angibt, ob schwache Verweise auch aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="593f2-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="593f2-107">Wenn `enumerateWeakReferences` `true`ist, enthält der `ppEnum`-Enumerator sowohl starke Verweise als auch schwache Verweise.</span><span class="sxs-lookup"><span data-stu-id="593f2-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="593f2-108">Wenn `enumerateWeakReferences` `false`ist, enthält der Enumerator nur starke Verweise.</span><span class="sxs-lookup"><span data-stu-id="593f2-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="593f2-109">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) -Enumerationsobjekts, bei dem es sich um einen Enumerator für die Objekte handelt, für die eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="593f2-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="593f2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="593f2-110">Remarks</span></span>  
 <span data-ttu-id="593f2-111">Diese Methode bietet eine Möglichkeit, die vollständige rooting-Kette für ein beliebiges verwaltetes Objekt in einem Prozess zu bestimmen, und kann verwendet werden, um zu bestimmen, warum ein Objekt noch aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="593f2-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="593f2-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="593f2-112">Requirements</span></span>  
 <span data-ttu-id="593f2-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="593f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="593f2-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="593f2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="593f2-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="593f2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="593f2-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="593f2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593f2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="593f2-117">See also</span></span>

- [<span data-ttu-id="593f2-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="593f2-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="593f2-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="593f2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
