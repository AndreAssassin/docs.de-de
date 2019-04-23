---
title: GetRealProcAddress-Funktion
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4723fbf2311316184cb77c90754d7e037badcd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089581"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="61120-102">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="61120-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="61120-103">Ruft die Adresse der angegebenen Funktion, die aus der neuesten installierten Version der common Language Runtime (CLR) exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="61120-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="61120-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="61120-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61120-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61120-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61120-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61120-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="61120-107">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="61120-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="61120-108">[out] Der Speicherort, der einen Zeiger auf die Adresse der Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="61120-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61120-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61120-109">Return Value</span></span>  
 <span data-ttu-id="61120-110">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="61120-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="61120-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="61120-111">Return code</span></span>|<span data-ttu-id="61120-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61120-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="61120-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="61120-113">S_OK</span></span>|<span data-ttu-id="61120-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="61120-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="61120-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="61120-115">E_POINTER</span></span>|<span data-ttu-id="61120-116">`ppv` ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="61120-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="61120-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="61120-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="61120-118">Die Funktion wird von der Laufzeit nicht exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="61120-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61120-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61120-119">Requirements</span></span>  
 <span data-ttu-id="61120-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61120-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61120-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61120-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61120-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61120-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61120-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61120-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61120-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61120-124">See also</span></span>

- [<span data-ttu-id="61120-125">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="61120-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
