---
title: COR_FIELD-Struktur
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2efe159eaa8b49d4d3825e9737593d0a12fc4d4c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740735"
---
# <a name="corfield-structure"></a>COR_FIELD-Struktur
Bietet Informationen zu einem Feld in einem Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`token`|Ein `mdFieldDef` Token, das zum Abrufen von Feldinformationen verwendet werden kann.|  
|`offset`|Der Offset in Bytes, die die Feld-Daten in das Objekt.|  
|`id`|Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Wert, der den Typ dieses Felds angibt.|  
|`fieldType`|Ein Wert der CorElementType-Enumeration, der den Typ des Felds angibt.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
