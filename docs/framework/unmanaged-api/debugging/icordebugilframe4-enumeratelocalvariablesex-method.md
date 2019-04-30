---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f9d20eda8684a9a5ae43c6240d0f8a9722c4d97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995513"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="952f4-102">ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode</span><span class="sxs-lookup"><span data-stu-id="952f4-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="952f4-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="952f4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="952f4-104">Ruft einen Enumerator für die lokale Variable im Rahmen ab, und schließt optional Variablen ein, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="952f4-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="952f4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="952f4-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="952f4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="952f4-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="952f4-107">[in] Ein [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob die Variablen in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, im Rahmen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="952f4-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="952f4-108">[out] Ein Zeiger auf die Adresse des "ICorDebugValueEnum"-Objekts, das den Enumerator für die lokalen Variablen in diesem Frame ist.</span><span class="sxs-lookup"><span data-stu-id="952f4-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="952f4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="952f4-109">Remarks</span></span>  
 <span data-ttu-id="952f4-110">Diese Methode ähnelt der [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) -Methode, mit dem Unterschied, dass sie optional auf Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt zugreift.</span><span class="sxs-lookup"><span data-stu-id="952f4-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="952f4-111">Festlegen von `flags` zu `ILCODE_ORIGINAL_IL` entspricht dem Aufruf [ICorDebugILFrame:: EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="952f4-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="952f4-112">Die Einstellung von `flags` auf `ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="952f4-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="952f4-113">Ist die Intermediate Language (IL) nicht instrumentiert, ist die Enumeration leer und die Methode gibt `S_OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="952f4-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="952f4-114">Der Enumerator schließt möglicherweise nicht alle lokalen Variablen in die ausgeführte Methode ein, da einige von ihnen möglicherweise nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="952f4-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="952f4-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="952f4-115">Requirements</span></span>  
 <span data-ttu-id="952f4-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="952f4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="952f4-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="952f4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="952f4-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="952f4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="952f4-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="952f4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952f4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="952f4-120">See also</span></span>

- [<span data-ttu-id="952f4-121">ICorDebugILFrame4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="952f4-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="952f4-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="952f4-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="952f4-123">ReJIT: Einen Leitfaden zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="952f4-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
