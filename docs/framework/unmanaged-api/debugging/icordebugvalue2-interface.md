---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0925cf217afafe57abf82cf51a77b1992bad5152
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966826"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="3bfce-102">ICorDebugValue2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bfce-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="3bfce-103">Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3bfce-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bfce-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3bfce-104">Methods</span></span>  
  
|<span data-ttu-id="3bfce-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3bfce-105">Method</span></span>|<span data-ttu-id="3bfce-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bfce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bfce-107">GetExactType-Methode</span><span class="sxs-lookup"><span data-stu-id="3bfce-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="3bfce-108">Ruft einen Schnittstellen Zeiger auf ein `ICorDebugType` -Objekt ab, <xref:System.Type> das den dieses Werts darstellt.</span><span class="sxs-lookup"><span data-stu-id="3bfce-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bfce-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bfce-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3bfce-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3bfce-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bfce-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bfce-111">Requirements</span></span>  
 <span data-ttu-id="3bfce-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bfce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfce-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3bfce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bfce-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bfce-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bfce-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bfce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bfce-116">See also</span></span>

- [<span data-ttu-id="3bfce-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3bfce-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="3bfce-118">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bfce-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
