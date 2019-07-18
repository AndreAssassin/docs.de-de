---
title: FunctionIDMapper-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9dee1404a8da63208bba7b7529b16eabbee3254
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745761"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper-Funktion
Benachrichtigt Sie den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) Rückrufe für diese Funktion. Mit `FunctionIDMapper`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Funktionsbezeichner, der neu zugeordnet werden soll.  
  
 `pbHookFunction`  
 [out] Ein Zeiger auf ein Wert, der der Profiler wird auf `true` , wenn sie empfangen möchte `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe; andernfalls wird dieser Wert auf `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls erzeugt ein Rückgabewert von null zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionIDMapper` Funktion ist ein Rückruf. Die Implementierung erfolgt durch den Profiler an einen anderen Bezeichner eine Funktions-ID neu zuordnen, die für den Profiler nützlicher ist. Die `FunctionIDMapper` gibt zurück, die alternative ID für eine bestimmte Funktion verwendet werden. Berücksichtigt die ausführungs-Engine dann die Anfrage des Profilers übergeben Sie diese alternative ID zusätzlich zu der herkömmlichen Funktions-ID, zurück an dem Profiler in den `clientData` Parameter der `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Hooks, um zu identifizieren die Funktion für die der Hook aufgerufen wird.  
  
 Können Sie die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) Methode an die Implementierung der `FunctionIDMapper` Funktion. Rufen Sie die `ICorProfilerInfo::SetFunctionIDMapper` Methode nur einmal, und es wird empfohlen, haben also in der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.  
  
 Es wird standardmäßig davon ausgegangen, dass ein Profiler, die das COR_PRF_MONITOR_ENTERLEAVE-Flag mithilfe von festlegt [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), und die Hooks über [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) oder [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), erhalten die `FunctionEnter2`, `FunctionLeave2`, und `FunctionTailcall2` Rückrufe für jede Funktion. Allerdings Profiler implementiert möglicherweise `FunctionIDMapper` selektiv vermeiden diese Rückrufe für bestimmte Funktionen durch Festlegen von `pbHookFunction` zu `false`.  
  
 Profiler sollte der Fälle fehlertoleranten sein, in denen mehrere Threads einer Anwendung ein Profil erstellt wurde gleichzeitig die gleiche Methode/Funktion aufrufen. In solchen Fällen erhält der Profiler kann mehrere `FunctionIDMapper` Rückrufe für den gleichen `FunctionID`. Der Profiler sollte sichergestellt sein, um die Werte von diesem Rückruf zurückgeben, wenn sie mehrere Male, mit dem gleichen aufgerufen wird `FunctionID`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [SetFunctionIDMapper-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
