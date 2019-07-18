---
title: ICorProfilerCallback4::GetReJITParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03b7ca218318df517832d198e72d4f79d30827b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779239"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters-Methode
Ermöglicht den Codeprofiler alternativen codeerstellungskennzeichen für einen neuen Methodentext für die neu kompilierte festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Das Modul, das die Methode enthält, für die die CLR die JIT-Neukompilierung-Parameter benötigt.  
  
 `methodId`  
 [in] Die `MethodDef` der Methode für die die CLR die JIT-Neukompilierung-Parameter benötigt.  
  
 `pFunctionControl`  
 [in] Ein Zeiger auf ein [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) -Schnittstelle, die der Profiler verwendet werden kann, um JIT-Neukompilierung Informationen für die Methode erneut kompiliert wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Probleme bei der CLR eine `GetReJITParameters` Rückruf, damit der Profiler die Parameter für die erneute Kompilierung einer bestimmten Methode angeben kann. Die `GetReJITParameters` Rückruf wird nur einmal pro Funktion ausgegeben, die Parameter, die vom Profiler bereitgestellte gelten für alle Instanzen dieser Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [JITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
