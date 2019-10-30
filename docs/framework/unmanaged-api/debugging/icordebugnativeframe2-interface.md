---
title: ICorDebugNativeFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: bff6dea0e870cf62734fa583eefa481c594481b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096523"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="e9d1a-102">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9d1a-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="e9d1a-103">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9d1a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e9d1a-104">Methods</span></span>  
  
|<span data-ttu-id="e9d1a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e9d1a-105">Method</span></span>|<span data-ttu-id="e9d1a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9d1a-107">IsChild-Methode</span><span class="sxs-lookup"><span data-stu-id="e9d1a-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="e9d1a-108">Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="e9d1a-109">IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="e9d1a-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="e9d1a-110">Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="e9d1a-111">GetStackParameterSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e9d1a-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="e9d1a-112">Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d1a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d1a-113">Remarks</span></span>  
 <span data-ttu-id="e9d1a-114">Diese Schnittstelle erweitert logisch die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9d1a-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e9d1a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d1a-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9d1a-116">Requirements</span></span>  
 <span data-ttu-id="e9d1a-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d1a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d1a-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9d1a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9d1a-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9d1a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9d1a-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d1a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d1a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d1a-121">See also</span></span>

- [<span data-ttu-id="e9d1a-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9d1a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e9d1a-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e9d1a-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
