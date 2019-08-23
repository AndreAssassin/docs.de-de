---
title: ICorDebugAppDomain2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63772c6642cc6f7f96a375beab4f7ef1b4884139
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959844"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="4af94-102">ICorDebugAppDomain2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4af94-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="4af94-103">Stellt Methoden bereit, um mit Arrays, Zeigern, Funktions Zeigern und Verweis Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4af94-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="4af94-104">Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4af94-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4af94-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4af94-105">Methods</span></span>  
  
|<span data-ttu-id="4af94-106">Methode</span><span class="sxs-lookup"><span data-stu-id="4af94-106">Method</span></span>|<span data-ttu-id="4af94-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4af94-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4af94-108">GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="4af94-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="4af94-109">Ruft ein Array vom angegebenen Typ oder einen Zeiger oder einen Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="4af94-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="4af94-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="4af94-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="4af94-111">Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="4af94-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4af94-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4af94-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4af94-113">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4af94-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af94-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4af94-114">Requirements</span></span>  
 <span data-ttu-id="4af94-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af94-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af94-116">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="4af94-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af94-117">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af94-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af94-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af94-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af94-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4af94-119">See also</span></span>

- [<span data-ttu-id="4af94-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4af94-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
