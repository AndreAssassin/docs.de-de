---
title: ICorDebugRegisterSet::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecbcff0fd124b94aeeecf82e23d9875c34ebb9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091576"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext-Methode
Ruft den Kontext des aktuellen Threads ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `contextSize`  
 [in] Die Größe in Bytes, der die `context` Array.  
  
 `context`  
 [in, out] Ein Array von Bytes, aus denen die Win32 `CONTEXT` Struktur für die aktuelle Plattform.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger sollte diese Funktion anstelle der Win32-Aufrufen `GetThreadContext` Funktion, da der Thread im Zustand "gehackte" sein kann, in dem der Kontext vorübergehend geändert wurde. Die zurückgegebenen Daten sind eine Win32- `CONTEXT` Struktur für die aktuelle Plattform.  
  
 Für nichtblatt-Frames, sollten Clients überprüfen, welche Register gültig sind, mithilfe von [ICorDebugRegisterSet:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
