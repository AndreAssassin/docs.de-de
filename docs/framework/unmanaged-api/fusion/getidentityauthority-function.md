---
title: GetIdentityAuthority-Funktion
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127147"
---
# <a name="getidentityauthority-function"></a>GetIdentityAuthority-Funktion
Ruft einen Zeiger auf eine [IIdentityAuthority](iidentityauthority-interface.md) -Instanz ab, die Schlüssel für Code Objekte verwaltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `ppIIdentityAuthority`  
 vorgenommen Der zurückgegebene `IIdentityAuthority` Zeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IIdentityAuthority-Schnittstelle](iidentityauthority-interface.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
