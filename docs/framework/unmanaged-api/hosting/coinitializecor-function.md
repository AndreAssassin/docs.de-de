---
title: CoInitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e8d65e739504e01a7d11b37d1b34d7313b13a5e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138334"
---
# <a name="coinitializecor-function"></a>CoInitializeCor-Funktion
`CoInitializeCor` ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 Um die Common Language Runtime zu initialisieren, verwenden Sie entweder [corbindtoriuntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [corbindtoken currentruntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Cor. h  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
