---
title: ICorProfilerInfo5::SetEventMask2-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868381"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>ICorProfilerInfo5::SetEventMask2-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Ereignisbenachrichtigungen von der Common Language Runtime (CLR) erhalten soll. Sie bietet mehr Funktionen als die [ICorProfilerInfo:: Log Test](icorprofilerinfo-seteventmask-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `dwEventsLow`  
 [in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt. Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.  
  
 `dwEventsHigh`  
 [in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.  Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp. Die Bits werden in der [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) -Enumeration beschrieben.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetEventMask2`-Methode wird verwendet, um die Rückrufe festzulegen, die der Profiler abonniert. In der Regel wird die [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) -Methode aufgerufen, um zu bestimmen, welche Bits festgelegt sind, eine logische OR-`pdwEventsLow` und `pdwEventsHigh` Werte sowie alle neuen Bits, die Sie festlegen möchten, und dann die `SetEventMask2`-Methode aufruft.  
  
 Diese Methode ist die empfohlene Alternative zur Methode " [" der Methode](icorprofilerinfo-seteventmask-method.md) "" von "".  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo5-Schnittstelle](icorprofilerinfo5-interface.md)
- [GetEventMask2-Methode](icorprofilerinfo5-geteventmask2-method.md)
