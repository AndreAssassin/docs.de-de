---
title: ICorDebugInternalFrame2::GetFrameAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c30115a23f7f73662c9b3f4f4a09d45478ad687
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995474"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress-Methode
Gibt die Stack-Adresse des internen Frames zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAddress`  
 [out] Zeiger auf die `CORDB_ADDRESS` für den internen Frame.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Adresse des internen Frames wurde erfolgreich zurückgegeben.|  
|E_FAIL|Die Adresse des internen Frames kann nicht zurückgegeben werden.|  
|E_INVALIDARG|`pAddress` ist `null`.|  
  
## <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert in `pAddress` können verwendet werden, um die Position des internen Frames relativ zu anderen Frames im Stapel zu bestimmen. Auch auf IA-64-basierten Computern internen Frames befindet sich nur auf dem Stapel, und keine entsprechenden Zeiger in einen Sicherungsspeicher.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugInternalFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
