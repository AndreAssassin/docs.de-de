---
title: IMetaDataValidate::ValidatorInit-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 177bd67e9f177296cf436e3c2537b95b30e34e87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766892"
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit-Methode
Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Überprüfungsfehler.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwModule`  
 [in] Der Wert der [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.  
  
 `pUnk`  
 [in] Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Instanz, die als Funktionsrückruf für Validierungsfehler dient.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataValidate-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
