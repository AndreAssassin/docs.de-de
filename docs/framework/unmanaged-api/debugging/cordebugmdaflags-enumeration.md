---
title: CorDebugMDAFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 732523935eec62bffbc15705bc93c97f14c90064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148420"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="3773f-102">CorDebugMDAFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3773f-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="3773f-103">Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="3773f-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3773f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3773f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3773f-105">Member</span><span class="sxs-lookup"><span data-stu-id="3773f-105">Members</span></span>  
  
|<span data-ttu-id="3773f-106">Member</span><span class="sxs-lookup"><span data-stu-id="3773f-106">Member</span></span>|<span data-ttu-id="3773f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3773f-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="3773f-108">Der Thread, der auf dem der MDA ausgelöst wurde hat verschoben, da der MDA ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="3773f-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3773f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3773f-109">Remarks</span></span>  
 <span data-ttu-id="3773f-110">Wenn nicht mehr die Aufrufliste beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread damit betrachtet *verlegt*.</span><span class="sxs-lookup"><span data-stu-id="3773f-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="3773f-111">Dies ist eine ungewöhnliche Situation eingehen, die durch die Ausführung einen ungültigen Vorgang beim Beenden des Threads.</span><span class="sxs-lookup"><span data-stu-id="3773f-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3773f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3773f-112">Requirements</span></span>  
 <span data-ttu-id="3773f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3773f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3773f-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3773f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3773f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3773f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3773f-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3773f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3773f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3773f-117">See also</span></span>

- [<span data-ttu-id="3773f-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3773f-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
