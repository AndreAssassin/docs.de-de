---
title: ICorDebugILFrame4::GetCodeEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d61981d26d21ec1e5e24093817586ebf45b129e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988480"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="d9d0d-102">ICorDebugILFrame4::GetCodeEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d9d0d-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="d9d0d-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="d9d0d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d9d0d-104">Ruft einen Zeiger auf den Code ab, der vom Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d0d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9d0d-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9d0d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9d0d-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="d9d0d-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die intermediate Language (IL), die von der Profiler ReJIT-Anfrage definiert, die im Rahmen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="d9d0d-108">[out] Ein Zeiger auf die Adresse ein "ICorDebugCode"-Objekt, das den Code darstellt, den diesen Stapelrahmen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d0d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9d0d-109">Remarks</span></span>  
 <span data-ttu-id="d9d0d-110">Diese Methode ähnelt der [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) -Methode, mit dem Unterschied, dass sie optional auf Code von der Profiler ReJIT-Anfrage definiert zugreift.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="d9d0d-111">Beim Aufruf dieser Methode eine `flags` Wert `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); Wenn die Methode instrumentiert ist, die IL nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="d9d0d-112">`ILCODE_REJIT_IL` ermöglicht dem Debugger auf den IL-Code durch der Profiler ReJIT-Anfrage definiert.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="d9d0d-113">Wenn die IL nicht instrumentiert wurde, `ppCode` ist **null**, und die Methode gibt `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="d9d0d-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9d0d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9d0d-114">Requirements</span></span>  
 <span data-ttu-id="d9d0d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9d0d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9d0d-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9d0d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9d0d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9d0d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9d0d-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d0d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d0d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d0d-119">See also</span></span>

- [<span data-ttu-id="d9d0d-120">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9d0d-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="d9d0d-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9d0d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d9d0d-122">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="d9d0d-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
