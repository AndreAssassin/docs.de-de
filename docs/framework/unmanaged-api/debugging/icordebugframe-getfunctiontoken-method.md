---
title: ICorDebugFrame::GetFunctionToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50e5fcee3705e05aeed820cf736613c12b00e50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754871"
---
# <a name="icordebugframegetfunctiontoken-method"></a>ICorDebugFrame::GetFunctionToken-Methode
Ruft das Metadatentoken für die Funktion, die den Code für diesen Stapelrahmen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pToken`  
 [out] Ein Zeiger auf ein `mdMethodDef` Token, die Metadaten für die Funktion verweist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
