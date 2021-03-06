---
title: ICorProfilerCallback::UnmanagedToManagedTransition-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: c381d4a85a1e836f1972060c8182dd698bb27550
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870534"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition-Methode
Benachrichtigt den Profiler, dass ein Übergang von nicht verwaltetem Code zu verwaltetem Code erfolgt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 in Die ID der Funktion, die aufgerufen wird.  
  
 `reason`  
 in Ein Wert der [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) -Enumeration, der angibt, ob der Übergang aufgrund eines Aufrufs von verwaltetem Code aus nicht verwaltetem Code oder aufgrund einer Rückgabe von einer nicht verwalteten Funktion, die von einem verwalteten Code aufgerufen wurde, aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert von `reason` COR_PRF_TRANSITION_RETURN und `functionId` nicht NULL ist, entspricht die Funktions-ID der nicht verwalteten Funktion und wurde nie mit dem JIT-Compiler (Just-in-Time) kompiliert. Nicht verwalteten Funktionen sind einige grundlegende Informationen zugeordnet, z. b. ein Name und einige Metadaten.  
  
 Wenn der Wert `reason` COR_PRF_TRANSITION_CALL ist, kann es vorkommen, dass die aufgerufene Funktion (d. h. die verwaltete Funktion) noch nicht JIT-kompiliert wurde.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ManagedToUnmanagedTransition-Methode](icorprofilercallback-managedtounmanagedtransition-method.md)
- [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Verwenden von C++-Interop (implizites PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
