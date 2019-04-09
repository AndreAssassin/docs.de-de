---
title: ICLRGCManager2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a89a7ef34418163d790fd055de681c1cdf989e57
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226910"
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2-Schnittstelle
Enthält Methoden, die einen Host für die Interaktion mit der common Language Runtime, Garbage Collection-System zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetGCStartupLimitsEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|Legt die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 fest. Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).  
  
 Die common Language Runtime (CLR) implementiert, die Garbage Collection-Mechanismus, mit der verwalteten <xref:System.GC> Typ. Weitere Informationen zur Garbage Collection-Systems finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Automatic Memory Management](../../../../docs/standard/automatic-memory-management.md)
- [COR_GC_STATS-Struktur](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
