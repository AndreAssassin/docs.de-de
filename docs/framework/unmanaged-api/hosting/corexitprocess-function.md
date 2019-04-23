---
title: CorExitProcess-Funktion
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b95625cfe17b36c0244e6780a08dcf50ce50763d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201857"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="7168c-102">CorExitProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="7168c-102">CorExitProcess Function</span></span>
<span data-ttu-id="7168c-103">Beendet den aktuellen nicht verwalteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="7168c-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="7168c-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="7168c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="7168c-105">Verwenden der [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="7168c-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7168c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7168c-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7168c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7168c-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="7168c-108">Eine ganze Zahl, die Exitcode des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="7168c-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7168c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7168c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7168c-110">Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` jede gestartete Laufzeit im Prozess nicht nur die Laufzeit, die legacy-APIs gebunden wurden, beendet.</span><span class="sxs-lookup"><span data-stu-id="7168c-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7168c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7168c-111">Requirements</span></span>  
 <span data-ttu-id="7168c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7168c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7168c-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7168c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7168c-114">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7168c-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7168c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7168c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7168c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7168c-116">See also</span></span>

- [<span data-ttu-id="7168c-117">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="7168c-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
