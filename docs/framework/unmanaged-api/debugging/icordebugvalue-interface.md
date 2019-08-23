---
title: ICorDebugValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bb2f6333f306c8a19c8b2f67986b23819b74ee0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966863"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="b1b8d-102">ICorDebugValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1b8d-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="b1b8d-103">Stellt einen Wert in dem Prozess dar, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="b1b8d-104">Der Wert kann ein Lese-oder ein Schreib Wert sein.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1b8d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b1b8d-105">Methods</span></span>  
  
|<span data-ttu-id="b1b8d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b1b8d-106">Method</span></span>|<span data-ttu-id="b1b8d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1b8d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1b8d-108">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="b1b8d-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="b1b8d-109">Diese Methode ist zurzeit nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="b1b8d-110">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="b1b8d-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="b1b8d-111">Ruft die Adresse dieses `ICorDebugValue` -Objekts ab, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="b1b8d-112">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b1b8d-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="b1b8d-113">Ruft die Größe des `ICorDebugValue` -Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="b1b8d-114">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="b1b8d-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="b1b8d-115">Ruft den primitiven Typ dieses `ICorDebugValue` -Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b8d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1b8d-116">Remarks</span></span>  
 <span data-ttu-id="b1b8d-117">Im Allgemeinen wird der Besitz eines Wert Objekts bei der Rückgabe übermittelt.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="b1b8d-118">Der Empfänger ist dafür verantwortlich, einen Verweis aus dem-Objekt zu entfernen, wenn er mit dem-Objekt fertig ist.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="b1b8d-119">Abhängig davon, wo der Wert aus abgerufen wurde, bleibt der Wert möglicherweise nicht gültig, nachdem der Prozess fortgesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="b1b8d-120">Im Allgemeinen sollte der Wert nicht über einen Aufrufen der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode hinweg aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1b8d-121">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b8d-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-122">Requirements</span></span>  
 <span data-ttu-id="b1b8d-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b8d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b8d-124">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b1b8d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1b8d-125">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1b8d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1b8d-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b8d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b8d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1b8d-127">See also</span></span>

- [<span data-ttu-id="b1b8d-128">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1b8d-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="b1b8d-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
