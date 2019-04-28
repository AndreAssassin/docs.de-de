---
title: ETaskType-Enumeration
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627962"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="fb1ab-102">ETaskType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fb1ab-102">ETaskType Enumeration</span></span>
<span data-ttu-id="fb1ab-103">Enthält Werte, die den Typ der Aufgabe angeben, indem Sie entweder dargestellt wird, ein [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) oder [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb1ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb1ab-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="fb1ab-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb1ab-105">Members</span></span>  
  
|<span data-ttu-id="fb1ab-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb1ab-106">Member</span></span>|<span data-ttu-id="fb1ab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb1ab-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="fb1ab-108">Die Schnittstelle stellt eine Aufgabe zur Entladung einer Anwendung dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="fb1ab-109">Die Schnittstelle stellt einen Debugger-Hilfsprogramm-Task dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="fb1ab-110">Die Schnittstelle stellt einen Finalizer-Task dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="fb1ab-111">Die Schnittstelle stellt eine Garbage Collection-Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="fb1ab-112">Die Schnittstelle stellt einen Gate-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="fb1ab-113">Die Schnittstelle stellt eine e/a-Thread-Aufgabe oder Thread eine Abschlussaufgabe-Port dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="fb1ab-114">Die Schnittstelle stellt einen Timer-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="fb1ab-115">Die Schnittstelle stellt einen Wait-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="fb1ab-116">Die Schnittstelle stellt eine Aufgabe der Worker-Threads dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="fb1ab-117">Der Task ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="fb1ab-118">Die Schnittstelle stellt eine Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="fb1ab-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb1ab-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb1ab-119">Requirements</span></span>  
 <span data-ttu-id="fb1ab-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb1ab-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb1ab-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb1ab-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb1ab-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb1ab-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb1ab-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb1ab-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb1ab-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb1ab-124">See also</span></span>

- [<span data-ttu-id="fb1ab-125">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fb1ab-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
