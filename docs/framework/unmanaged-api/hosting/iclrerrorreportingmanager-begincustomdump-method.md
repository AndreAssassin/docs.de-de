---
title: ICLRErrorReportingManager::BeginCustomDump-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cb6cd8d31e01ea2f1749a6cb4d17173679f0c06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104109"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump-Methode
Gibt die Konfiguration von benutzerdefinierten Heap-Speicherabbildern für die Fehlerberichterstattung.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwFlavor`  
 [in] Ein [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) Wert, der die Art des auf dem das benutzerdefinierte Heap-Speicherabbild erstellen angibt.  
  
 `dwNumItems`  
 [in] Die Länge der `items` Array. Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `dwNumItems` sollte Null sein.  
  
 `items`  
 [in] Ein Array von [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) -Instanzen, die für die hinzuzufügenden Minidump Elemente angeben. Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `items` sollte null sein.  
  
 `dwReserved`  
 [in] Für die zukünftige Verwendung reserviert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `BeginCustomDump` Methode legt die benutzerdefinierte Konfiguration von Heapdumps fest. Die [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) Methode löscht die Konfiguration des benutzerdefinierten Heap-Speicherabbild und alle zugeordneten Zustand freigibt. Es sollte aufgerufen werden, nachdem das benutzerdefinierte Heap-Speicherabbild abgeschlossen ist.  
  
> [!IMPORTANT]
>  Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CustomDumpItem-Struktur](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [ECustomDumpFlavor-Enumeration](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
