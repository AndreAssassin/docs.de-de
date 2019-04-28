---
title: FunctionIDMapper2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a236dcae29d00afe3b72dce8f81d657fb4fac28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598921"
---
# <a name="functionidmapper2-function"></a>FunctionIDMapper2-Funktion
Benachrichtigt Sie den Profiler, dass der angegebene Bezeichner einer Funktion einer alternativen ID zu verwendende zugeordnet werden kann die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), oder[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Rückrufe für diese Funktion. Mit `FunctionIDMapper2`kann der Profiler auch angeben, ob er Rückrufe für diese Funktion empfangen will.  
  
## <a name="syntax"></a>Syntax  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Funktionsbezeichner, der neu zugeordnet werden soll.  
  
 `clientData`  
 [in] Ein Zeiger auf Daten, mit denen Mehrdeutigkeiten zwischen Laufzeiten aufgelöst werden.  
  
 `pbHookFunction`  
 [out] Ein Zeiger auf einen Wert, den der Profiler auf `true` festlegt, wenn er die Rückrufe `FunctionEnter3`, `FunctionLeave3` und `FunctionTailcall3` oder `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo` und `FunctionTailcall3WithInfo` empfangen möchte. Andernfalls wird der Wert auf `false` festgelegt.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Profiler gibt einen Wert zurück, den die Ausführungs-Engine als alternativen Funktionsbezeichner verwendet. Der Rückgabewert darf nicht NULL sein, es sei denn, in `false` wird `pbHookFunction` zurückgegeben. Andernfalls führt ein Rückgabewert von NULL zu unvorhersehbaren Ergebnissen, einschließlich des möglichen Anhaltens des Prozesses.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion mit einem zusätzlichen Parameter, die zum Übergeben von Clientdaten verwendet wird. Die Clientdaten werden verwendet, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3::SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
