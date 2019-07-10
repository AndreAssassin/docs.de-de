---
title: ICorDebugILFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d7eca3c2825707c9190436377bba7e4bb0d5447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757975"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP-Methode
Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnOffset`  
 [out] Der Wert des Anweisungszeigers.  
  
 `pMappingResult`  
 [out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des Anweisungszeigers wird der Stapelrahmen-Offset in der Microsoft intermediate Language (MSIL) Funktionscode. Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste Anweisung ausführen. Wenn der Stapelrahmen nicht aktiv ist, ist diese Adresse die nächste Anweisung ausgeführt werden, wenn der Stapelrahmen erneut aktiviert wird.  
  
 Wenn dieser Rahmen eine just-in-Time (JIT) kompilierten Rahmen ist, wird der Wert des Anweisungszeigers Zuordnung rückwärts von den tatsächlichen systemeigenen Anweisungszeiger, daher der Wert möglicherweise nur ungefähr ermittelt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
