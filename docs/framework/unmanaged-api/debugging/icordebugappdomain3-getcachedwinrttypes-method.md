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
ms.openlocfilehash: 89f45208550d49f214e763728ddc9eb1bfcd9800
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088974"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="8dd31-102">ICorDebugAppDomain3::GetCachedWinRTTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="8dd31-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="8dd31-103">Ruft einen Enumerator für alle zwischengespeicherten Windows-Runtime Typen ab.</span><span class="sxs-lookup"><span data-stu-id="8dd31-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dd31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dd31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dd31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8dd31-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="8dd31-106">vorgenommen Ein Zeiger auf ein [icordebugguidtotypeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) -Schnittstellen Objekt, das die verwalteten Darstellungen von Windows-Runtime Typen aufzählen kann, die zurzeit in der Anwendungsdomäne geladen sind.</span><span class="sxs-lookup"><span data-stu-id="8dd31-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dd31-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8dd31-107">Requirements</span></span>  
 <span data-ttu-id="8dd31-108">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="8dd31-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="8dd31-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dd31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dd31-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dd31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dd31-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd31-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dd31-112">See also</span></span>

- [<span data-ttu-id="8dd31-113">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8dd31-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
