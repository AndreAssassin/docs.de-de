---
title: ICorDebugStackWalk::GetContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224857"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext-Methode
Gibt den Kontext für den aktuellen Frame in der [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `contextFlags`  
 [in] Flags, die den angeforderten Inhalt des Kontextpuffers (definiert in "Winnt.h") angeben.  
  
 `contextBufSize`  
 [in] Die Größe der reservierten des Kontextpuffers.  
  
 `contextSize`  
 [out] Die tatsächliche Größe des Kontexts. Dieser Wert muss kleiner als oder gleich der Größe des Kontextpuffers.  
  
 `contextBuf`  
 [out] Der Kontextpuffer.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Kontext für den aktuellen Frame wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der Kontext konnte nicht zurückgegeben werden.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Der Kontextpuffer ist zu klein.|  
|CORDBG_E_PAST_END_OF_STACK|Die Frame-Pointer ist bereits am Ende des Stapels. aus diesem Grund können keine zusätzlichen Frames zugegriffen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Da nur eine Teilmenge der Register, z. B. nicht flüchtigen Register, entladen wiederhergestellt werden. entspricht der Kontext möglicherweise nicht exakt dem registrierungszustand zum Zeitpunkt des Aufrufs.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
