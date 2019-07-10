---
title: ICorDebugCode::CreateBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747731"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="6c448-102">ICorDebugCode::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="6c448-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="6c448-103">Erstellt einen Haltepunkt in diesem Codesegment am angegebenen Offset.</span><span class="sxs-lookup"><span data-stu-id="6c448-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c448-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c448-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c448-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c448-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6c448-106">[in] Der Offset, an der den Haltepunkt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c448-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="6c448-107">[out] Ein Zeiger auf die Adresse ein "ICorDebugFunctionBreakpoint"-Objekt, das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c448-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c448-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c448-108">Remarks</span></span>  
 <span data-ttu-id="6c448-109">Bevor Sie der Haltepunkt aktiv ist, müssen sie das Prozessobjekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6c448-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="6c448-110">Wenn dieser Code ist die Microsoft intermediate Language (MSIL)-Code ein, und es ein just-in-Time (JIT gibt)-kompilierte, systemeigene Version des Codes, der Haltepunkt wird in der JIT-kompiliertem Code auch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c448-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="6c448-111">(Der gleiche ist true, wenn der Code JIT-kompilierten höher ist.)</span><span class="sxs-lookup"><span data-stu-id="6c448-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c448-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c448-112">Requirements</span></span>  
 <span data-ttu-id="6c448-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c448-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c448-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c448-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c448-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c448-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c448-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c448-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c448-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c448-117">See also</span></span>
