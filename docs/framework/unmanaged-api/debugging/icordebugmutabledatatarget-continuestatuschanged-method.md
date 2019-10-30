---
title: 'Icordebugmutabledatatarget:: continuestatuschangi-Methode'
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: abaf2d0542e16f526ecbe369370c31c225808f1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139352"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="bf559-102">Icordebugmutabledatatarget:: continuestatuschangi-Methode</span><span class="sxs-lookup"><span data-stu-id="bf559-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="bf559-103">Ändert den Fortsetzungsstatus für das ausstehende Debugereignis für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="bf559-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf559-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf559-104">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf559-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf559-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="bf559-106">Der vom Betriebssystem definierte Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="bf559-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="bf559-107">Ein [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)-Wert, der den neuen angeforderten Fortsetzungsstatus angibt.</span><span class="sxs-lookup"><span data-stu-id="bf559-107">A [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf559-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf559-108">Remarks</span></span>  
 <span data-ttu-id="bf559-109">Der Debugger ruft die `ContinueStatusChanged`-Methode auf, wenn er eine ICorDebug-Methode aufruft, die erfordert, dass das aktuelle Debugereignis auf eine Weise behandelt wird, die sich möglicherweise von der Weise unterscheidet, auf die es normalerweise behandelt würde.</span><span class="sxs-lookup"><span data-stu-id="bf559-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="bf559-110">Gibt es beispielsweise eine ausstehende Ausnahme, und der Debugger fordert einen Vorgang an, der die Ausnahme abbrechen würde (z.B. [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder `FuncEval`), wird über diese API angefordert, dass die Ausnahme abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="bf559-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf559-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf559-111">Requirements</span></span>  
 <span data-ttu-id="bf559-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf559-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf559-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf559-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf559-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf559-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf559-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf559-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf559-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf559-116">See also</span></span>

- [<span data-ttu-id="bf559-117">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf559-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="bf559-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bf559-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
