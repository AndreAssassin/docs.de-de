---
title: ICorDebugObjectValue::GetFieldValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fc65f5b55082970a0cd59a6850aaaa6779d0821
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766404"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue-Methode
Ruft den Wert des angegebenen Felds der angegebenen Klasse für den Wert dieses Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pClass`  
 [in] Ein Zeiger auf ein "ICorDebugClass"-Objekt, das die Klasse für den abzurufenden Wert des Felds darstellt.  
  
 `fieldDef`  
 [in] Ein `mdFieldDef` -Token, die Metadaten zum Beschreiben des Felds verweist.  
  
 `ppValue`  
 [out] Ein Zeiger auf ein "ICorDebugValue"-Objekt, das den Wert des angegebenen Felds darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse, die im angegebenen die `pClass` -Parameter muss in der Hierarchie, der den Objektwert-Klasse, und das Feld muss ein Feld der Klasse sein.  
  
 Die `GetFieldValue` Methode ist für generische Objekte und die generischen Klassen dennoch erfolgreich. Z. B. wenn MyDictionary\<V > erbt von Wörterbuch\<"string", "V >, und der Objektwert ist vom Typ MyDictionary\<int32 >, und übergeben Sie die `ICorDebugClass` Objekt für das Wörterbuch\<K, V > wird ein Feld des Wörterbuchs abgerufen\<String, int32 >.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
