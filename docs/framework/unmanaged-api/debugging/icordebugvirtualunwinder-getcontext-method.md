---
title: ICorDebugVirtualUnwinder::GetContext-Methode
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3125fd5081e68237714bcb10f760b73ce7509f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119222"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>ICorDebugVirtualUnwinder::GetContext-Methode
Ruft den aktuellen Kontext dieses Entladers ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `contextFlags`  
 [in] Flags, die angeben, welche Teile des Kontexts zurückgegeben werden (in "WinNT.h" definiert).  
  
 `cbContextBuf`  
 [in] Die Anzahl von Bytes in `contextBuf`.  
  
 `contextSize`  
 [out] Ein Zeiger auf die Anzahl der tatsächlich in `contextBuf` geschriebenen Bytes.  
  
 `contextBuf`  
 [out] Ein Bytearray, das den aktuellen Kontext dieses Entladers enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Alle von "mscordbi" empfangenen HRESULT-Fehlerwerte gelten als schwerwiegend und bewirken, dass "ICorDebug"-APIs `CORDBG_E_DATA_TARGET_ERROR` zurückgeben.  
  
## <a name="remarks"></a>Hinweise  
 Den anfänglichen Wert festlegen die `contextBuf` Argument auf den Kontextpuffer zurückgegeben, indem die [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
 Da beim Entladen möglicherweise nur eine Teilmenge der Register (z. B. nur die nicht permanenten Register) wiederhergestellt werden, stimmt der Kontext möglicherweise nicht genau mit dem Registrierungszustand zum Zeitpunkt des eigentlichen Methodenaufrufs überein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMemoryBuffer-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
