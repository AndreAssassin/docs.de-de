---
title: ICorDebugRegisterSet-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135238"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet-Schnittstelle
Stellt den Satz von Registern zur Verfügung, auf dem Computer, der gerade Code ausführt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRegisters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|Ruft den Wert jedes Register (auf dem Computer, die gerade Code ausführt) ab, das durch die Bitmaske angegeben ist.|  
|[GetRegistersAvailable-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|Ruft eine Bitmaske, der angibt, welche Register in diesem `ICorDebugRegisterSet` sind derzeit verfügbar.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|Ruft den Kontext des aktuellen Threads ab.|  
|[SetRegisters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|Für .NET Framework, Version 2.0 implementiert nicht.|  
|[SetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|Für .NET Framework 2.0 implementiert nicht.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugRegisterSet` -Schnittstelle unterstützt nur 32-Bit-Register. Verwenden der [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) Schnittstelle auf Plattformen wie z. B. IA-64, zusätzliche Register zu erfordern.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
