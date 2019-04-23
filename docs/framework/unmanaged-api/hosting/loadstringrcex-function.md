---
title: LoadStringRCEx-Funktion
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 697557463aa949036acb21e63b9a82b1fb84b415
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105494"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="05458-102">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="05458-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="05458-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="05458-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="05458-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="05458-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05458-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05458-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05458-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="05458-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="05458-107">[in] Ein Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="05458-107">[in] A culture identifier.</span></span> <span data-ttu-id="05458-108">Übergeben Sie-1 für `lcid` die Standardkultur verwenden.</span><span class="sxs-lookup"><span data-stu-id="05458-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="05458-109">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="05458-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="05458-110">[out] Ein Puffer, der die Fehlermeldung nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="05458-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="05458-111">[in] Die Größe des Puffers für die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="05458-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="05458-112">[in] Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="05458-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="05458-113">[out] Ein Zeiger auf die Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="05458-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05458-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05458-114">Return Value</span></span>  
 <span data-ttu-id="05458-115">Diese Methode gibt die standard-COM-Fehlercodes, zurück, wie in "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="05458-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="05458-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="05458-116">Return code</span></span>|<span data-ttu-id="05458-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05458-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="05458-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="05458-118">S_OK</span></span>|<span data-ttu-id="05458-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="05458-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="05458-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="05458-120">E_INVALIDARG</span></span>|<span data-ttu-id="05458-121">`szBuffer` null ist, oder `iMax` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="05458-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05458-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05458-122">Remarks</span></span>  
 <span data-ttu-id="05458-123">Wenn die Methode nicht erfolgreich abgeschlossen wird `szBuffer` enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="05458-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05458-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05458-124">Requirements</span></span>  
 <span data-ttu-id="05458-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05458-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05458-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05458-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05458-127">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05458-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05458-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05458-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05458-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05458-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="05458-130">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="05458-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="05458-131">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="05458-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
