---
title: ICorDebugEval::Abort-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 78402e5e099815fe309618e692285de91b8b29f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124240"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort-Methode
Bricht die Berechnung ab, die dieses ICorDebugEval-Objekt gerade ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Auswertung geschnistet und nicht die neueste ist, schlägt die `Abort` Methode möglicherweise fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
