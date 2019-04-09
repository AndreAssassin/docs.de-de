---
title: ICorPublish::EnumProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116294"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="b46c4-102">ICorPublish::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="b46c4-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="b46c4-103">Ruft einen Enumerator für die verwaltete Prozesse auf diesem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b46c4-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b46c4-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b46c4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b46c4-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="b46c4-106">Der Wert der [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) Enumeration, der angibt, den Typ des Prozesses abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b46c4-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="b46c4-107">In der aktuellen Version ist nur COR_PUB_MANAGEDONLY gültig.</span><span class="sxs-lookup"><span data-stu-id="b46c4-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="b46c4-108">Ein Zeiger auf die Adresse einer [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) -Instanz, die der Enumerator, der Prozesse ist.</span><span class="sxs-lookup"><span data-stu-id="b46c4-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b46c4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b46c4-109">Remarks</span></span>  
 <span data-ttu-id="b46c4-110">Der Enumerator die Auflistung der Prozesse wird auf Grundlage einer Momentaufnahme der Prozesse, die beim Ausführen der `EnumProcesses` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b46c4-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="b46c4-111">Der Enumerator enthält keine Prozesse, die vor dem Beenden oder starten Sie nach `EnumProcesses` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b46c4-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="b46c4-112">Die `EnumProcesses` Methode kann mehrmals aufgerufen werden, dazu [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) Instanz eine neue aktuelle Auflistung von Prozessen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b46c4-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="b46c4-113">Vorhandene Sammlungen nicht betroffen von nachfolgenden Aufrufen der `EnumProcesses` Methode.</span><span class="sxs-lookup"><span data-stu-id="b46c4-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46c4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b46c4-114">Requirements</span></span>  
 <span data-ttu-id="b46c4-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b46c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46c4-116">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b46c4-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b46c4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b46c4-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b46c4-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b46c4-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b46c4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b46c4-119">See also</span></span>

- [<span data-ttu-id="b46c4-120">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b46c4-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
