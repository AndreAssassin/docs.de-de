---
title: ICorDebugRegisterSet::GetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b417685361126951470571e2440cc842ab1c94fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782908"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters-Methode
Ruft den Wert jedes Register (auf dem Computer, die gerade Code ausführt) ab, das durch die Bitmaske angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mask`  
 [in] Eine Bitmaske, die angibt, welche Register Werte abgerufen werden sollen. Jedes Bit entspricht einer registrieren. Wenn ein bit auf 1 festgelegt ist, wird der Wert des Registers abgerufen. Andernfalls wird der Wert des Registers nicht abgerufen werden.  
  
 `regCount`  
 [in] Die Anzahl der Registerwerte abgerufen werden sollen.  
  
 `regBuffer`  
 [out] Ein Array von `CORDB_REGISTER` Objekte, von denen jede einen Wert eines Registers empfängt.  
  
## <a name="remarks"></a>Hinweise  
 Die Größe des Arrays sollte gleich der Anzahl der Bits, die auf einen in der Bitmaske festgelegt werden. Die `regCount` Parameter gibt die Anzahl der Elemente im Puffer, der die Registerwerte empfängt. Wenn die `regCount` Wert ist zu klein für die Anzahl von Registern der Maske, die höhere nummerierten Register aus dem Satz gekürzt. Wenn die `regCount` Wert ist zu groß ist, die nicht verwendeten `regBuffer` Elemente nicht geändert werden.  
  
 Wenn die Bitmaske ein Registers angibt, der nicht verfügbar ist, `GetRegisters` gibt einen unbestimmten Wert für diese registrieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
