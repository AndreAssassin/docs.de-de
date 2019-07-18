---
title: ICLRTaskManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763372"
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager-Schnittstelle
Stellt Methoden, die dem Host explizit anfordern, die die common Language Runtime (CLR) ermöglichen Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe zu erhalten, und legen Sie die geografische Sprache und Kultur für den Task.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Fordert explizit an, dass die CLR erstellen Sie ein neues [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.|  
|[GetCurrentTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Ruft die `ICLRTask` -Instanz, die die Aufgabe darstellt, die gerade ausgeführt wird.|  
|[GetCurrentTaskType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Ruft den Typ der Aufgabe, die gerade ausgeführt wird.|  
|[SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Benachrichtigt die CLR, dass der Host den Gebietsschemabezeichner für die aktuell ausgeführte Aufgabe geändert hat.|  
|[SetUILocale-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Benachrichtigt, dass der Host den Gebietsschemabezeichner der Benutzeroberfläche für die derzeit ausgeführte Aufgabe geändert hat der common Language Runtime.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird verfügt über Darstellungen, die beide auf der Hostseite (eine Instanz von [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) und auf der CLR-Seite (eine Instanz von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). Entweder der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die Hostseite Darstellung muss mit einer entsprechenden CLR-Seite-Darstellung, um sicherzustellen, dass erfolgreiche Kommunikation zwischen dem Host und die CLR in Bezug auf die Aufgabe verknüpft werden. Die beiden Objekte müssen erstellt und instanziiert wird, bevor verwalteter Code in einem Betriebssystem-Thread ausgeführt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
