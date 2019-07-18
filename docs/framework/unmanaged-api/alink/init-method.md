---
title: Init-Methode
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 606809533010f458272cd6fbbad6234217bddea2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741619"
---
# <a name="init-method"></a>Init-Methode
Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pDispenser`  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf den Metadatenverteiler.  
  
 `pErrorHandler`  
 [IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle die Fehlerbehandlung.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
