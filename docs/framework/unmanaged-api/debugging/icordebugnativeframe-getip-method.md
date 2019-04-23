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
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073532"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP-Methode
Ruft der systemeigene Code offset-Speicherort, der der Anweisungszeiger derzeit festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
