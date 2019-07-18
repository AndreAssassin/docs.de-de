---
title: ICorDebugHeapValue::IsValid-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca3b86e90dcb76c1fece44cf2c5ed68e073d8e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757218"
---
# <a name="icordebugheapvalueisvalid-method"></a>ICorDebugHeapValue::IsValid-Methode
Ruft einen Wert, der angibt, ob das durch diesen ICorDebugHeapValue dargestellte Objekt gültig ist.  
  
 Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbValid`  
 [out] Ein Zeiger auf einen booleschen Wert, der angibt, ob dieser Wert auf dem Heap gültig ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert ist ungültig, wenn es vom Garbage Collector freigegeben wurde.  
  
 Diese Methode ist veraltet. In .NET Framework 2.0, alle Werte sind gültig bis [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufgerufen wird, an der Zeit werden die Werte ungültig sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
