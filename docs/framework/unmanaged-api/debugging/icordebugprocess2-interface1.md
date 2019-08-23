---
title: ICorDebugProcess2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5519714ff2b4ee67d0e59001bf5b454cdc25d648
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961079"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2-Schnittstelle
Eine logische Erweiterung der ICorDebugProcess-Schnittstelle, die einen Prozess darstellt, der verwalteten Code ausführt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Entfernt einen Haltepunkt am angegebenen Offset, der durch einen früheren-Aufrufsatz `ICorDebugProcess2::SetUnmanagedBreakpoint`festgelegt wurde.|  
|[GetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Ruft die Flags ab, die für die Common Language Runtime (CLR) festgelegt werden müssen, um das Bild in den Prozess `ICorDebugProcess2`zu laden, auf den von verwiesen wird.|  
|[GetReferenceValueFromGCHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Ruft einen Verweis Zeiger auf das angegebene verwaltete Objekt ab, das über ein Garbage Collection Handle verfügt.|  
|[GetThreadForTaskID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Ruft den Thread ab, in dem die Aufgabe mit dem angegebenen Bezeichner ausgeführt wird.|  
|[GetVersion-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Ruft die Version der CLR ab, auf der der Prozess ausgeführt wird, der debuggt wird.|  
|[SetDesiredNGENCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Legt die Flags fest, die für den Just-in-time (JIT)-Compiler erforderlich sind, um ein Bild in den Prozess zu laden, der gedebuggt wird.|  
|[SetUnmanagedBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Abbild Offset fest.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
