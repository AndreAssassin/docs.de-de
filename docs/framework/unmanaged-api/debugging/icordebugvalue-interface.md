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
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227820"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="788aa-102">ICorDebugValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="788aa-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="788aa-103">Stellt einen Wert in der gedebuggte Prozess.</span><span class="sxs-lookup"><span data-stu-id="788aa-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="788aa-104">Der Wert kann es sich um einen Lesevorgang oder einen Write-Wert sein.</span><span class="sxs-lookup"><span data-stu-id="788aa-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="788aa-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="788aa-105">Methods</span></span>  
  
|<span data-ttu-id="788aa-106">Methode</span><span class="sxs-lookup"><span data-stu-id="788aa-106">Method</span></span>|<span data-ttu-id="788aa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="788aa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="788aa-108">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="788aa-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="788aa-109">Diese Methode wird derzeit nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="788aa-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="788aa-110">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="788aa-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="788aa-111">Ruft die Adresse dieses `ICorDebugValue` -Objekt, das gerade gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="788aa-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="788aa-112">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="788aa-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="788aa-113">Ruft die Größe in Bytes, davon `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="788aa-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="788aa-114">GetType-Methode</span><span class="sxs-lookup"><span data-stu-id="788aa-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="788aa-115">Ruft den primitiven Typ dieses `ICorDebugValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="788aa-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="788aa-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="788aa-116">Remarks</span></span>  
 <span data-ttu-id="788aa-117">Im Allgemeinen wird den Besitz eines Wertobjekts übergeben, wenn er zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="788aa-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="788aa-118">Der Empfänger ist verantwortlich für das Entfernen von Verweisen aus dem Objekt, wenn sie mit dem Objekt abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="788aa-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="788aa-119">Je nachdem, in denen der Wert abgerufen wurde kann der Wert nicht gültig bleiben, nachdem der Prozess fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="788aa-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="788aa-120">Also im Allgemeinen der Wert darf nicht gespeichert werden über einen Aufruf der der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="788aa-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="788aa-121">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="788aa-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788aa-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="788aa-122">Requirements</span></span>  
 <span data-ttu-id="788aa-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="788aa-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="788aa-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="788aa-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="788aa-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="788aa-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="788aa-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788aa-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788aa-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="788aa-127">See also</span></span>

- [<span data-ttu-id="788aa-128">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="788aa-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="788aa-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="788aa-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
