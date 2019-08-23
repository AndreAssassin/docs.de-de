---
title: ICorDebugProcess5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ecea4857dabc55e8acd3c22a025895a686efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931089"
---
# <a name="icordebugprocess5-interface"></a>ICorDebugProcess5-Schnittstelle
Erweitert die ICorDebugProcess-Schnittstelle, um den Zugriff auf den verwalteten Heap zu unterstützen, um Informationen über Garbage Collection verwalteter Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus dem lokalen Anwendungssystem eigenen Image Cache lädt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnableNGENPolicy-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Legt einen Wert fest, der bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.|  
|[EnumerateGCReferences-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Ruft einen Enumerator für alle Objekte ab, die in einem Prozess in eine Garbage Collection aufgenommen werden sollen.|  
|[EnumerateHandles-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Ruft einen Enumerator für Objekt Handles in einem Prozess ab.|  
|[EnumerateHeap-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Ruft einen Enumerator für Objekte im verwalteten Heap ab.|  
|[EnumerateHeapRegions-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Ruft einen Enumerator für Bereiche des verwalteten Heaps ab.|  
|[GetArrayLayout-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Ruft Informationen über das Layout eines Arrays im Arbeitsspeicher ab.|  
|[GetGCHeapInformation-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Ruft einen Zeiger auf eine [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Struktur ab, die Informationen zu Objekten enthält, die auf dem verwalteten Heap Garbage Collection ausgeführt werden sollen.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Ruft einen Zeiger auf ein Objekt auf dem verwalteten Heap ab.|  
|[GetTypeFields-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Ruft einen Zeiger auf ein Array ab, das Feldinformationen für einen Typ auf Grundlage des Typbezeichners enthält.|  
|[GetTypeForTypeID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Ruft ein Type-Objekt ab, das Informationen zu einem-Objekt auf der Grundlage seiner Typbezeichner bereitstellt.|  
|[GetTypeID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Ruft den Typbezeichner für das-Objekt an einer angegebenen Adresse ab.|  
|[GetTypeLayout-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erweitert logisch die ICorDebugProcess-, ICorDebugProcess2-und [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) -Schnittstellen.  
  
> [!NOTE]
> Diese Schnittstelle bietet keine Unterstützung für das Remote Aufrufen von einem anderen Computer oder von einem anderen Prozess.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
