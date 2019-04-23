---
title: ModuleBindInfo-Struktur
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124448"
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo-Struktur
Enthält ausführliche Informationen über das Modul verwiesen wird und die Assembly, die sie enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwAppDomainId`|Ein eindeutiger Bezeichner für die `IStream` zurückgegeben, die durch einen Aufruf der [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) -Methode aus der das Modul verwiesen wird, ist geladen werden.|  
|`lpAssemblyIdentity`|Ein eindeutiger Bezeichner für die Assembly mit dem Modul verwiesen wird.|  
|`lpModuleName`|Der Name des Moduls auf die verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 `ModuleBindInfo` wird als Parameter übergeben, `IHostAssemblyStore::ProvideModule`. Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR). Nach einem Aufruf von der [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) Methode zurückgegeben wird, die Runtime den Bezeichner verwendet, um zu bestimmen, ob der Inhalt des der `IStream` zugeordnet wurde. Wenn dies der Fall ist, lädt die Runtime den Stream neu zuzuordnen, anstatt die vorhandene Kopie. Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Datenströme, die von Aufrufen zurückgegeben werden die `IHostAssemblyStore::ProvideAssembly` Methode. Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport sowie für Anforderungen von Assembly eindeutig sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [AssemblyBindInfo-Struktur](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
