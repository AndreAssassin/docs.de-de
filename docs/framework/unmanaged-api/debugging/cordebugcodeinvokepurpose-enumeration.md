---
title: CorDebugCodeInvokePurpose-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b5de58caeeac5ae85402e91a1402958e68336bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967596"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>CorDebugCodeInvokePurpose-Aufzählung
Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Keine oder unbekannt.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Der verwaltete Code führt alle verwalteten Einstiegspunkte (z. B. umgekehrte p-invoke-Punkte) auf. Sämtliche detailliertere Zwecke sind in der Laufzeit unbekannt.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Der verwaltete Code führt einen statischen Konstruktor aus.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Der verwaltete Code führt die Implementierung für eine bestimmte Schnittstellenmethode aus, die aufgerufen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird von der [ICorDebugProcess6:: getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) -Methode verwendet, um Informationen über das Durchlaufen von verwaltetem Code bereitzustellen.  
  
> [!NOTE]
> Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
