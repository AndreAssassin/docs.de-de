---
title: _EFN_GetManagedExcepStack-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61f4e057a487462feb385ca0e3ca977fdd165f56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739090"
---
# <a name="efngetmanagedexcepstack-function"></a>\_EFN\_GetManagedExcepStack-Funktion
Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Client`  
 [in] Der Client, der gedebuggt wird.  
  
 `StackObjAddr`  
 [in] Ein Zeiger des verwalteten Objekts abgeleitet <xref:System.Exception>.  
  
 szStackString  
 [out] Die zurückgegebene Zeichenfolge.  
  
 `cbString`  
 [out] Die Anzahl der Zeichen in den Puffer verfügbar.  
  
## <a name="remarks"></a>Hinweise  
 Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und Fehlercode 0 x 1000 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace.h  
  
 **.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
