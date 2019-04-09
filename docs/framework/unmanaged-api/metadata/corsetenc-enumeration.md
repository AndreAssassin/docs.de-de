---
title: CorSetENC-Enumeration
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122316"
---
# <a name="corsetenc-enumeration"></a>CorSetENC-Enumeration
Enthält Werte, mit denen das Verhalten während der Generierung von Metadaten beeinflusst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDSetENCOn`|Veraltet.|  
|`MDSetENCOff`|Veraltet.|  
|`MDUpdateENC`|Gibt an, dass die Metadaten aktualisiert werden kann, Token nicht verschoben werden können.|  
|`MDUpdateFull`|Gibt an, dass das Token, die während eines Updates verschoben werden können.|  
|`MDUpdateExtension`|Gibt an, dass Updates nur aus Hinzufügungen bestehen können. Token können nicht verschoben werden.|  
|`MDUpdateIncremental`|Gibt an, dass die Kompilierung inkrementell ist.|  
|`MDUpdateDelta`|Gibt an, dass nur geänderte Metadaten gespeichert werden soll.|  
|`MDUpdateMask`|Enthält `MDUpdateENC`, `MDUpdateFull` und `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
