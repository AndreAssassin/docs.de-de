---
title: IHostSyncManager::CreateManualEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cfb57ba6f07437abfc8576ca4d5ff9cd0131d8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753438"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a>IHostSyncManager::CreateManualEvent-Methode
Erstellt ein Ereignis für manuelles Zurücksetzen-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bInitialState`  
 [in] `true`, wenn das Objekt signalisiert, andernfalls wird `false`.  
  
 `ppEvent`  
 [out] Ein Zeiger auf die Adresse einer [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) -Instanz oder null, wenn das Ereignis konnte nicht erstellt werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CreateManualEvent` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.|  
  
## <a name="remarks"></a>Hinweise  
 `CreateManualEvent` erstellt eine `IHostManualEvent`, ein Ereignis für manuelles Zurücksetzen-Objekt, das einen Aufruf erfordert die [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) Methode, um es auf einen nicht signalisierten Zustand festgelegt. `CreateManualEvent` spiegelt die Win32- `CreateEvent` Funktion mit einem Wert von `true` für die `bManualReset` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostManualEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [IHostSyncManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
