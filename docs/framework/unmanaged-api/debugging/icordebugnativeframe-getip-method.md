---
title: ICorDebugNativeFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e9149bafc866f89253c4318ac69f2705431e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765303"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP-Methode
Ruft der systemeigene Code offset-Speicherort, der der Anweisungszeiger derzeit festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnOffset`  
 [out] Ein Zeiger auf die Offsetposition im nativen Code.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Stapelrahmen, der durch diesen "ICorDebugNativeFrame" dargestellt wird, aktiv ist, ist der Offset der Adresse, der die nächste Anweisung ausgeführt werden. Wenn dieses Stapelrahmens nicht aktiv ist, ist der Offset der Adresse der nächsten Anweisung wird ausgeführt, wenn der Stapelrahmen erneut aktiviert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
