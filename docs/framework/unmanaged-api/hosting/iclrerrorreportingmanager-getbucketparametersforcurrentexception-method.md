---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cb2a8d2a4e089d16b6c2129c165a9d8b6828f3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141730"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a>ICLRErrorReportingManager::GetBucketParametersForCurrentException-Methode
Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.  
  
 Ein *Bucket* ist eine Sammlung von Daten von Fehlern, die mit den gleichen Codefehler verknüpft ist. *Dr. Watson* bezieht sich auf eine Reihe von Technologien zum Sammeln und Analysieren von Daten, die eine Ausnahme zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pParams`  
 [out] Ein Zeiger auf eine [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) Struktur, die Fehlerdaten, die für die ausgelöste Ausnahme enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
