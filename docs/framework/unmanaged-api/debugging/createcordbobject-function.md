---
title: CreateCordbObject-Funktion
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965827"
---
# <a name="createcordbobject-function"></a>CreateCordbObject-Funktion
Erstellt eine Debugschnittstelle ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iDebuggerVersion`  
 [in] Debuggerversion des Zielprozesses. Dieser Parameter muss CorDebugVersion_2_0 für das Remotedebuggen sein.  
  
 `ppCordb`  
 [out] Zeiger auf einen Zeiger auf ein Objekt, das in umgewandelt werden, wird ein [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle und zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_INVALIDARG  
 `ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Schnittstelle, die in zurückgegebenen `ppCordb` ist die Debugschnittstelle auf oberster Ebene, für alle Debugdienste verwalteten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
