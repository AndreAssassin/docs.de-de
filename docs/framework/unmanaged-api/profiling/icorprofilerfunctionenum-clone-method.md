---
title: ICorProfilerFunctionEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ffd1fcc36f0c6cc3c5f063c5a916e8918839566
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135589"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="d8a4b-102">ICorProfilerFunctionEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="d8a4b-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="d8a4b-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d8a4b-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8a4b-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8a4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8a4b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d8a4b-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der, die wiederum auf eine Kopie dieses zeigt [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d8a4b-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="d8a4b-107">Die Kopie des Enumerators verwaltet einen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d8a4b-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d8a4b-108">Allerdings ist die Kopie in die ursprüngliche Cursorposition Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="d8a4b-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a4b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8a4b-109">Requirements</span></span>  
 <span data-ttu-id="d8a4b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a4b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a4b-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8a4b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8a4b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8a4b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d8a4b-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d8a4b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8a4b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8a4b-114">See also</span></span>

- [<span data-ttu-id="d8a4b-115">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8a4b-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="d8a4b-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d8a4b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
