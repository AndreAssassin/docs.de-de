---
title: ICorDebugComObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783969"
---
# <a name="icordebugcomobjectvalue-interface"></a>ICorDebugComObjectValue-Schnittstelle
Stellt Methoden bereit, um Informationen abzurufen, die einem Runtime Callable Wrapper (RCW) zugeordnet sind.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetCachedInterfacePointers-Methode](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Ruft die unformatierten Schnittstellen Zeiger ab, die im aktuellen RCW zwischengespeichert werden.|  
|[GetCachedInterfaceTypes-Methode](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt geschrieben oder verwendet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Um zu überprüfen, ob eine Instanz einer ICorDebugValue-Schnittstelle einen RCW darstellt, Ruft ein Debugger `QueryInterface` für "ICorDebugValue" mit `IID_ICorDebugComObjectValue`auf.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
