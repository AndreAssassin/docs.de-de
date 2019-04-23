---
title: CorDeclSecurity-Enumeration
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136967"
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity-Enumeration
Gibt die Sicherheitsaktionen an, die mit deklarativer Sicherheit ausgeführt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dclActionMask`|Reserviert.|  
|`dclActionNil`|Reserviert.|  
|`dclRequest`|Reserviert.|  
|`dclDemand`|Allen Aufrufern einer höheren Ebene in der Aufrufliste muss die vom aktuellen Berechtigungsobjekt angegebene Berechtigung erteilt worden sein.|  
|`dclAssert`|Der aufrufende Code kann die durch das aktuelle Berechtigungsobjekt identifizierte Ressource zugreifen, selbst wenn Aufrufern einer höheren Ebene im Stapel nicht die Berechtigung zum Zugriff auf die Ressource erteilt wurde|  
|`dclDeny`|Auch wenn diese Berechtigung für den Zugriff erteilt wurde, wird Aufrufern, der Zugriff auf die durch das aktuelle Berechtigungsobjekt angegebene Ressource verweigert.|  
|`dclPermitOnly`|Nur auf die durch dieses Berechtigungsobjekt angegebenen Ressourcen kann zugegriffen werden, selbst wenn dem Code die Berechtigung für den Zugriff auf andere Ressourcen gewährt wurde.|  
|`dclLinktimeCheck`|Der direkte Aufrufer muss die angegebene Berechtigung für einen bestimmten Zeitraum erteilt worden sein.|  
|`dclInheritanceCheck`|Die abgeleitete Klasse erbt von einer anderen Klasse oder eine Methode überschreibt muss die angegebene Berechtigung erteilt worden sein.|  
|`dclRequestMinimum`|Der Aufrufer kann für die minimalen Berechtigungen für den auszuführenden Code anfordern. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclRequestOptional`|Der Aufrufer kann für zusätzliche Berechtigungen anfordern, die optional sind (zur Ausführung nicht erforderlich). Diese Anforderung lehnt implizit alle anderen nicht speziell angeforderten Berechtigungen ab. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclRequestRefuse`|Die Anforderung des Aufrufers für Berechtigungen, die missbraucht werden könnten, wird nicht gewährt werden. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclPrejitGrant`|Reserviert.|  
|`dclPrejitDenied`|Reserviert.|  
|`dclNonCasDemand`|Reserviert.|  
|`dclNonCasLinkDemand`|Dem unmittelbaren Aufrufer muss die angegebene Berechtigung erteilt worden sein.|  
|`dclNonCasInheritance`|Reserviert.|  
|`dclLinkDemandChoice`|Reserviert.|  
|`dclInheritanceDemandChoice`|Reserviert.|  
|`dclDemandChoice`|Reserviert.|  
|`dclMaximumValue`|Reserviert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
