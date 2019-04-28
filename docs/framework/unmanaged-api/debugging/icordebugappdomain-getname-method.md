---
title: ICorDebugAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7939f7b1c0c725bb4e8c642bc38121dd755da5e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785137"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays. Legen Sie diesen Wert auf 0 (null), diese Methode in den Abfragemodus zu platzieren.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Größe der den Namen oder die Anzahl der Zeichen im tatsächlich zurückgegebenen `szName`. Im Abfragemodus kann diesen Wert den Aufrufer wissen, wie großen einen Puffer für den Namen zuweisen.  
  
 `szName`  
 [out] Ein Array, das den Namen der Anwendungsdomäne speichert.  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugger Ruft die `GetName` -Methode einmal zum Abrufen der Größe eines Puffers für den Namen erforderlich sind. Der Debugger weist den Puffer zu, und klicken Sie dann ein zweites Mal Ruft die Methode, um den Puffer zu füllen. Der erste Aufruf, zum Abrufen der Größe des Namens, wird als bezeichnet *Abfragemodus*.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
