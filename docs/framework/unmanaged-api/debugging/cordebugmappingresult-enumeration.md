---
title: CorDebugMappingResult-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2042d0936359a85d203375c42be0d8a096f004e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739760"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="e3cca-102">CorDebugMappingResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e3cca-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="e3cca-103">Stellt Details darüber bereit, wie der Wert des Anweisungszeigers (IP) abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="e3cca-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3cca-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="e3cca-105">Member</span><span class="sxs-lookup"><span data-stu-id="e3cca-105">Members</span></span>  
  
|<span data-ttu-id="e3cca-106">Member</span><span class="sxs-lookup"><span data-stu-id="e3cca-106">Member</span></span>|<span data-ttu-id="e3cca-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3cca-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="e3cca-108">Der systemeigene Code ist im Prolog, sodass der Wert, der die IP-Adresse 0 ist.</span><span class="sxs-lookup"><span data-stu-id="e3cca-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="e3cca-109">Der systemeigene Code ist in einem Epilog, daher ist der Wert, der die IP-Adresse die Adresse der letzten Anweisung der Methode.</span><span class="sxs-lookup"><span data-stu-id="e3cca-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="e3cca-110">Keine Informationen über die Zuordnung ist für die Methode verfügbar, sodass der Wert, der die IP-Adresse 0 ist.</span><span class="sxs-lookup"><span data-stu-id="e3cca-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="e3cca-111">Obwohl der Zuordnungsinformationen für die Methode wird, kann nicht die aktuelle Adresse Microsoft intermediate Language (MSIL)-Code zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e3cca-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="e3cca-112">Der Wert, der die IP-Adresse ist 0.</span><span class="sxs-lookup"><span data-stu-id="e3cca-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="e3cca-113">Die Methode ordnet genau MSIL-Code oder der Frame hat interpretiert, sodass der Wert, der die IP-Adresse korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="e3cca-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="e3cca-114">Die Methode wurde erfolgreich zugeordnet, aber der Wert, der die IP-Adresse ist möglicherweise ungefähre.</span><span class="sxs-lookup"><span data-stu-id="e3cca-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3cca-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3cca-115">Remarks</span></span>  
 <span data-ttu-id="e3cca-116">Sie können die [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) Methode, um den Wert des Anweisungszeigers abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3cca-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3cca-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3cca-117">Requirements</span></span>  
 <span data-ttu-id="e3cca-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3cca-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3cca-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3cca-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3cca-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3cca-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3cca-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3cca-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cca-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3cca-122">See also</span></span>

- [<span data-ttu-id="e3cca-123">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e3cca-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
