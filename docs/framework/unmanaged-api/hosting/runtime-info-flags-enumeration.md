---
title: RUNTIME_INFO_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215687"
---
# <a name="runtimeinfoflags-enumeration"></a>RUNTIME_INFO_FLAGS-Enumeration
Enthält Werte, die angeben, welche Informationen über die common Language Runtime (CLR) zurückgegeben werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Gibt an, dass Verzeichnisinformationen nicht enthalten sein sollen.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Gibt an, dass keine Informationen zur Version enthalten sein sollen.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Gibt an, dass ein Fehlerdialogfeld bei einem Fehler nicht angezeigt werden soll.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Gibt an, dass die Auswirkungen des Aufrufs der [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion mit dem SEM_FAILCRITICALERRORS-Flag überschrieben werden soll. D. h. soll ein Dialogfeld für die Installation bei einem Fehler unterdrückt wird angezeigt werden.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Gibt eine Anforderung für Informationen zu einer AMD-64-kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_REQUEST_IA64`|Gibt eine Anforderung für Informationen zu einer IA-64-kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_REQUEST_X86`|Gibt eine Anforderung für Informationen zu einer X86 kompatible Version der Laufzeit an.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Gibt an, dass das Upgrade Versionsinformationen eingeschlossen werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Flags der Plattform-Architektur können angegebenen nur jeweils nur ein und können nicht kombiniert werden:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
