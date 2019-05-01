---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049712"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="90bd8-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="90bd8-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="90bd8-103">[Wird nur in der .NET Framework 4.7 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="90bd8-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="90bd8-104">Benachrichtigt den Profiler an, wenn JIT-Kompilierung einer dynamischen Methode abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="90bd8-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90bd8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="90bd8-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90bd8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="90bd8-106">Parameters</span></span>  
<span data-ttu-id="90bd8-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="90bd8-107">[in] `functionId`</span></span>  
<span data-ttu-id="90bd8-108">Der Bezeichner der in-Memory-Funktion, die für die JIT-Kompilierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="90bd8-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="90bd8-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="90bd8-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="90bd8-110">Ein Wert, der angibt, ob die JIT-Kompilierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="90bd8-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="90bd8-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="90bd8-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="90bd8-112">`true` um anzugeben, das blockieren die Laufzeit zu warten, bis der aufrufende Thread von diesem Rückruf zurück zur Folge haben. `false` um anzugeben, dass die Blockierung der Vorgang der Laufzeit nicht beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="90bd8-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="90bd8-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90bd8-113">Remarks</span></span>  

<span data-ttu-id="90bd8-114">Dieser Rückruf wird immer dann ausgelöst, wenn JIT-Kompilierung einer dynamischen Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="90bd8-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="90bd8-115">Dies umfasst verschiedene IL-Stubs und LCG-Methoden.</span><span class="sxs-lookup"><span data-stu-id="90bd8-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="90bd8-116">Das Ziel ist, die Profiler-Schreiber genügend Informationen zum Identifizieren der kompilierten Methode für Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="90bd8-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="90bd8-117">`functionId` Werte können nicht zum Auflösen in ihren Metadatentoken verwendet werden, da dynamische Methoden keine Metadaten haben.</span><span class="sxs-lookup"><span data-stu-id="90bd8-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="90bd8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90bd8-118">Requirements</span></span>  
 <span data-ttu-id="90bd8-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90bd8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90bd8-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90bd8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90bd8-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90bd8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90bd8-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="90bd8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bd8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90bd8-123">See also</span></span>

- [<span data-ttu-id="90bd8-124">DynamicMethodJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="90bd8-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="90bd8-125">ICorProfilerCallback8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90bd8-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
