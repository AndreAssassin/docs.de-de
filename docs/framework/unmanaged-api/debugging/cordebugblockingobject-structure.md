---
title: CorDebugBlockingObject-Struktur
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740394"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="b0de8-102">CorDebugBlockingObject-Struktur</span><span class="sxs-lookup"><span data-stu-id="b0de8-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="b0de8-103">Definiert ein Objekt, das blockiert einen Thread und die spezifische Ursache, dass der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="b0de8-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0de8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0de8-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="b0de8-105">Member</span><span class="sxs-lookup"><span data-stu-id="b0de8-105">Members</span></span>  
  
|<span data-ttu-id="b0de8-106">Member</span><span class="sxs-lookup"><span data-stu-id="b0de8-106">Member</span></span>|<span data-ttu-id="b0de8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0de8-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="b0de8-108">Das Objekt, auf dem der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="b0de8-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="b0de8-109">Dieses Objekt gilt nur für die Dauer des aktuellen Status "synchronisiert".</span><span class="sxs-lookup"><span data-stu-id="b0de8-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="b0de8-110">Wenn zwei Threads für dasselbe Objekt innerhalb der gleichen Status "synchronisiert" blockiert werden, erwarten Sie möglicherweise die [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) Methode, um den gleichen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b0de8-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="b0de8-111">Allerdings werden die Schnittstellen können oder möglicherweise keine äquivalente Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b0de8-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="b0de8-112">Die Anzahl der Millisekunden, bevor der blockierende Vorgang wird das Timeout, oder der Wert INFINITE, der angibt, dass es kein Timeout. Der Timeout-Wert gibt die Gesamtlänge der blockierende Vorgang, nicht die Zeit, die noch verbleibenden ist.</span><span class="sxs-lookup"><span data-stu-id="b0de8-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="b0de8-113">Der Grund für dieses Objekt der Thread blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="b0de8-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0de8-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0de8-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0de8-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0de8-115">Requirements</span></span>  
 <span data-ttu-id="b0de8-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0de8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0de8-117">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="b0de8-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b0de8-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0de8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0de8-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0de8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0de8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0de8-120">See also</span></span>

- [<span data-ttu-id="b0de8-121">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b0de8-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="b0de8-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b0de8-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
