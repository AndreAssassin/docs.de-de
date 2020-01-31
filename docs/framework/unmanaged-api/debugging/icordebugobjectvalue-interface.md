---
title: ICorDebugObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792687"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="c046f-102">ICorDebugObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c046f-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="c046f-103">Eine Unterklasse von "ICorDebugValue", die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="c046f-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c046f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c046f-104">Methods</span></span>  
  
|<span data-ttu-id="c046f-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-105">Method</span></span>|<span data-ttu-id="c046f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c046f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c046f-107">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="c046f-108">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-<xref:System.Type> des Objekts ab, auf das dieses `ICorDebugObjectValue` verweist.</span><span class="sxs-lookup"><span data-stu-id="c046f-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="c046f-109">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="c046f-110">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="c046f-110">Not implemented.</span></span>|  
|[<span data-ttu-id="c046f-111">GetFieldValue-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="c046f-112">Ruft einen Schnittstellen Zeiger auf einen [ICorDebugValue](icordebugvalue-interface.md) ab, der den Wert des angegebenen Felds der angegebenen Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c046f-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="c046f-113">GetManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="c046f-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="c046f-114">Obsolete.</span></span> <span data-ttu-id="c046f-115">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c046f-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="c046f-116">GetVirtualMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="c046f-117">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="c046f-117">Not implemented.</span></span>|  
|[<span data-ttu-id="c046f-118">IsValueClass-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="c046f-119">Ruft einen Wert ab, der angibt, ob das Objekt, auf das dieser `ICorDebugObjectValue` verweist, ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="c046f-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="c046f-120">SetFromManagedCopy-Methode</span><span class="sxs-lookup"><span data-stu-id="c046f-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="c046f-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="c046f-121">Obsolete.</span></span> <span data-ttu-id="c046f-122">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c046f-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c046f-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c046f-123">Remarks</span></span>  
 <span data-ttu-id="c046f-124">Ein `ICorDebugObjectValue` bleibt gültig, bis der Prozess, der debuggt wird, fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c046f-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c046f-125">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c046f-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c046f-126">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c046f-126">Requirements</span></span>  
 <span data-ttu-id="c046f-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c046f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c046f-128">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c046f-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c046f-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c046f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c046f-130">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c046f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c046f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c046f-131">See also</span></span>

- [<span data-ttu-id="c046f-132">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c046f-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
