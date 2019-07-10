---
title: ICorDebug::DebugActiveProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe94203d315c32b62a191adf294a9c1310fe28e0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738262"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="09e38-102">ICorDebug::DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="09e38-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="09e38-103">Wird der Debugger an einen vorhandenen Prozess angefügt.</span><span class="sxs-lookup"><span data-stu-id="09e38-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09e38-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09e38-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="09e38-106">[in] Die ID des Prozesses, für die der Debugger wird angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="09e38-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="09e38-107">[in] Boolescher Wert, der festgelegt wird, um `true` Wenn der Debugger sollte sich so wie Win32-Debugger für den Prozess Verhalten und die nicht verwalteten Rückrufe; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="09e38-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="09e38-108">[out] Ein Zeiger auf die Adresse ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, an dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="09e38-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09e38-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09e38-109">Remarks</span></span>  
 <span data-ttu-id="09e38-110">Interop-Debuggen wird auf Win9x und nicht-X86-Plattformen wie z. B. IA-64- und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09e38-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e38-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09e38-111">Requirements</span></span>  
 <span data-ttu-id="09e38-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09e38-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e38-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09e38-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09e38-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09e38-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09e38-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e38-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e38-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09e38-116">See also</span></span>

- [<span data-ttu-id="09e38-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09e38-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
