---
title: ICLRDebugging-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155713"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="00593-102">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00593-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="00593-103">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="00593-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00593-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="00593-104">Methods</span></span>  
  
|<span data-ttu-id="00593-105">Methode</span><span class="sxs-lookup"><span data-stu-id="00593-105">Method</span></span>|<span data-ttu-id="00593-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00593-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00593-107">OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="00593-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="00593-108">Ruft ab, der "ICorDebugProcess"-Schnittstelle, die eine common Language Runtime (CLR)-Modul in den Prozess geladenen entspricht.</span><span class="sxs-lookup"><span data-stu-id="00593-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="00593-109">CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="00593-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="00593-110">Bestimmt, ob eine Bibliothek, die vom bereitgestellt wurde ein [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle wird immer noch verwendet oder entladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="00593-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00593-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00593-111">Remarks</span></span>  
 <span data-ttu-id="00593-112">Sie erhalten eine Instanz von der `ICLRDebugging` -Schnittstelle mithilfe der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="00593-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00593-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00593-113">Requirements</span></span>  
 <span data-ttu-id="00593-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00593-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00593-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00593-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00593-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00593-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00593-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00593-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00593-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00593-118">See also</span></span>

- [<span data-ttu-id="00593-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="00593-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="00593-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="00593-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
