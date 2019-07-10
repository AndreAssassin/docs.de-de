---
title: CorDebugGenerationTypes-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193f5ffe96e89a00bed8a3c88ee346ba3ea9f2b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740014"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="feb54-102">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="feb54-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="feb54-103">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="feb54-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="feb54-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="feb54-105">Member</span><span class="sxs-lookup"><span data-stu-id="feb54-105">Members</span></span>  
  
|<span data-ttu-id="feb54-106">Membername</span><span class="sxs-lookup"><span data-stu-id="feb54-106">Member name</span></span>|<span data-ttu-id="feb54-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="feb54-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="feb54-108">Generation 0.</span><span class="sxs-lookup"><span data-stu-id="feb54-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="feb54-109">Generation 1.</span><span class="sxs-lookup"><span data-stu-id="feb54-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="feb54-110">Generation 2.</span><span class="sxs-lookup"><span data-stu-id="feb54-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="feb54-111">Der große Objektheap.</span><span class="sxs-lookup"><span data-stu-id="feb54-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feb54-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="feb54-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb54-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="feb54-113">Requirements</span></span>  
 <span data-ttu-id="feb54-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feb54-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb54-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feb54-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feb54-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feb54-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feb54-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb54-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb54-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feb54-118">See also</span></span>

- [<span data-ttu-id="feb54-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="feb54-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
