---
title: CorDebugEHClause-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839e698c8921f916fad174bae4f4cc8bb4d02994
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609073"
---
# <a name="cordebugehclause-structure"></a>CorDebugEHClause-Struktur
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt eine Ausnahmebehandlung (Exception Handling, EH)-Klausel für einen bestimmten Intermediate Language (IL)-Codeabschnitt dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`Flags`|Ein Bitfeld, das die Ausnahmeinformationen in der EH-Klausel beschreibt. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`TryOffset`|Der Offset, in Bytes, des `try`-Blocks vom Beginn des Methodentextes.|  
|`TryLength`|Die Länge, in Bytes, des `try`-Blocks.|  
|`HandlerOffset`|Der Speicherort des Handlers für diesen `try`-Block.|  
|`HandlerLength`|Die Größe des Handlercodes in Bytes.|  
|`ClassToken`|Der Metadatentoken für einen typenbasierten Ausnahmehandler.|  
|`FilterOffset`|Der Offset, in Bytes, vom Beginn des Methodentextes für einen filterbasierten Ausnahmehandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Array von `CoreDebugEHClause` Werte wird zurückgegeben, durch die [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) Methode.  
  
 Die Informationen der EH-Klausel werden durch die CLI-Spezifikation definiert. Weitere Informationen finden Sie unter [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Das `flags`-Feld kann die folgenden Flags enthalten. Beachten Sie, dass diese nicht in CorDebug.idl oder CorDebug.h definiert sind.  
  
|Flag|Wert|Beschreibung|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Eine typisierte Ausnahmeklausel.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Ein Ausnahmefilter und eine Handlerklausel.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|Eine `finally`-Klausel.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Eine fault-Klausel (eine `finally`-Klausel, die nur aufgerufen wird, wenn eine Ausnahme ausgelöst wird).|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetEHClauses-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
