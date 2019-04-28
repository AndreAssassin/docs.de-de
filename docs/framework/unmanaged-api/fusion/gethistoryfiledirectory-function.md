---
title: GetHistoryFileDirectory-Funktion
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697624"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="571ca-102">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="571ca-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="571ca-103">Ruft den Pfad des Anwendungsverzeichnisses Verlauf.</span><span class="sxs-lookup"><span data-stu-id="571ca-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="571ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="571ca-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="571ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="571ca-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="571ca-106">[out] Ein Puffer, die den Pfad zum Anwendungsverzeichnis Verlauf enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="571ca-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="571ca-107">[in, out] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="571ca-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="571ca-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="571ca-108">Return Value</span></span>  
 <span data-ttu-id="571ca-109">Diese Methode gibt die standard-COM-Fehlercodes, zurück, wie in der Datei "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="571ca-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="571ca-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="571ca-110">Return code</span></span>|<span data-ttu-id="571ca-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="571ca-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="571ca-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="571ca-112">S_OK</span></span>|<span data-ttu-id="571ca-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="571ca-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="571ca-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="571ca-114">E_INVALIDARG</span></span>|<span data-ttu-id="571ca-115">`wzDir` oder `pdwSize` ist Null, oder die Version Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="571ca-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="571ca-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="571ca-116">Remarks</span></span>  
 <span data-ttu-id="571ca-117">Bei erfolgreichem Abschluss der `pdwSize` Argument auf die Länge der Zeichenfolge für den Pfad festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="571ca-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="571ca-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="571ca-118">Requirements</span></span>  
 <span data-ttu-id="571ca-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="571ca-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="571ca-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="571ca-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="571ca-121">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="571ca-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="571ca-122">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="571ca-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="571ca-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="571ca-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571ca-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="571ca-124">See also</span></span>

- [<span data-ttu-id="571ca-125">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="571ca-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="571ca-126">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="571ca-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="571ca-127">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="571ca-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
