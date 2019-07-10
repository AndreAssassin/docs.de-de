---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec29aa748c437199434fa1394e1a00c82154447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766871"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub-Methode
Ruft einen Wert, der angibt, ob eine Adresse in einen Stub handelt, die einen Übergang in verwalteten Code bewirkt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Wert, der die fragliche Adresse angibt.  
  
 `pbTransitionStub`  
 [out] Ein Zeiger auf einen booleschen Wert, der `true` ist, die einen Übergang in verwalteten Code, führt die angegebene Adresse innerhalb eines Stubs andernfalls *`pbTransitionStub` ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die `IsTransitionStub` Methode kann von nicht verwalteten stepping-Code verwendet werden, wann die schrittweisen Kontrolle an die verwalteten zugeordnetem zurückgeben.  
  
 Sie können auch die Identity-Übergang-Stubs anhand der Informationen in der portierbaren ausführbaren Datei (PE)-Datei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
