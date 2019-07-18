---
title: ICorProfilerCallback6-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041542"
---
# <a name="icorprofilercallback6-interface"></a>ICorProfilerCallback6-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Eine Unterklasse von [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , die stellt einer Rückrufmethode, die die common Language Runtime verwendet, um einen Profiler zu benachrichtigen, die eine Assembly geladen wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAssemblyReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
