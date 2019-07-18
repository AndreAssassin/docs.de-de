---
title: ICorProfilerInfo3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3
helpviewer_keywords:
- ICorProfilerInfo3 interface [.NET Framework profiling]
ms.assetid: 044a262f-0fa7-485d-b0c1-64cdc359c654
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb0944829d9f33277fdf53ad78cc37878336434f
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486961"
---
# <a name="icorprofilerinfo3-interface"></a>ICorProfilerInfo3-Schnittstelle
Stellt Methoden bereit, mit denen Codeprofiler mit der CLR (Common Language Runtime) kommunizieren können, um die Ereignisüberwachung zu steuern und Informationen anzufordern. Die `ICorProfilerInfo3` Schnittstelle ist eine Erweiterung von der [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) Schnittstelle. Es bietet neue Methoden, die in der .NET Framework 4 und höheren Versionen unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumJITedFunctions-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)|Gibt einen Enumerator für alle zuvor mit JIT kompilierten Funktionen zurück.|  
|[EnumModules-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)|Gibt einen Enumerator zurück, der Methoden zum sequenziellen Iterieren durch eine Auflistung von verwalteten Modulen bereitstellt, die in die Anwendung geladen werden.|  
|[GetAppDomainsContainingModule-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Ruft die Bezeichner der Anwendungsdomänen ab, in denen das angegebene Modul geladen wurde.|  
|[GetFunctionEnter3Info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)|Stellt den Stapel Stapelrahmen und die Argumentinformationen der Funktion, die dem Profiler von gemeldet wird die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) funktionieren; kann nur während der aufgerufen werden die `FunctionEnter3WithInfo` Rückruf.|  
|[GetFunctionLeave3Info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)|Stellt den Stapelrahmen und den Rückgabewert der Funktion, die dem Profiler von gemeldet wird die [FunctionLeave3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) funktionieren; kann nur während der aufgerufen werden die `FunctionLeave3WithInfo` Rückruf.|  
|[GetFunctionTailcall3Info-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)|Stellt den Stapelrahmen der Funktion, die dem Profiler von gemeldet wird die [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) funktionieren; kann nur während der aufgerufen werden die `FunctionTailcall3WithInfo` Rückruf.|  
|[GetModuleInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)|Gibt bei Angabe einer Modul-ID den Dateinamen des Moduls, die ID der übergeordneten Assembly des Moduls und eine Bitmaske zurück, die die Eigenschaften des Moduls beschreibt.|  
|[GetRuntimeInformation-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getruntimeinformation-method.md)|Stellt die Versionsinformationen zum Laufzeitmodul bereit, für das ein Profil erstellt wird.|  
|[GetStringLayout2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadStaticAddress2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getthreadstaticaddress2-method.md)|Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.|  
|[RequestProfilerDetach-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)|Weist das Laufzeitmodul an, den Profiler zu trennen.|  
|[SetEnterLeaveFunctionHooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Gibt an, die vom Profiler implementierten Funktionen, die aufgerufen werden, auf die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) Funktionen.|  
|[SetEnterLeaveFunctionHooks3WithInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Gibt an, die vom Profiler implementierten Funktionen, die aufgerufen werden, auf die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Hooks von verwalteten Funktionen.|  
|[SetFunctionIDMapper2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)|Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden. Diese Methode erweitert [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) mit einem Parameter, die Tools für die profilerstellung verwenden können, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR implementiert die Methoden der `ICorProfilerInfo3`-Schnittstelle mithilfe des Freethreadmodells. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 Die CLR übergibt eine `ICorProfilerInfo3` -Schnittstelle an jeden Codeprofiler während der Initialisierung des Profilers und Implementierung der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) oder [ICorProfilerCallback3::I NitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) Methode. Ein Codeprofiler kann dann die `ICorProfilerInfo3`-Methoden aufrufen, um Informationen zu verwaltetem Code abzurufen, der unter der Kontrolle der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
