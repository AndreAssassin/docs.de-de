---
title: ICorDebugAppDomain3::GetCachedWinRTTypes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a08e83d67c973294938a030b95b906aec6be6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962603"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="10484-102">ICorDebugAppDomain3::GetCachedWinRTTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="10484-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="10484-103">Ruft einen Enumerator für alle zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen.</span><span class="sxs-lookup"><span data-stu-id="10484-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10484-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10484-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="10484-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10484-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="10484-106">[out] Ein Zeiger auf ein [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) Schnittstellenobjekts, das die verwaltete Darstellung der aufzählen kann [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen, die derzeit in der Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="10484-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10484-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10484-107">Requirements</span></span>  
 <span data-ttu-id="10484-108">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10484-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="10484-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10484-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10484-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10484-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10484-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10484-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10484-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10484-112">See also</span></span>

- [<span data-ttu-id="10484-113">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10484-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
