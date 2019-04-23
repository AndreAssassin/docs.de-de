---
title: GetFileVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d25a3ccdd66ff7acb70f1f5e6c60157b53cc97c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123726"
---
# <a name="getfileversion-function"></a><span data-ttu-id="b5b6b-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="b5b6b-102">GetFileVersion Function</span></span>
<span data-ttu-id="b5b6b-103">Ruft die common Language Runtime (CLR) Versionsinformationen von der angegebenen Datei, die mithilfe des angegebenen Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="b5b6b-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b6b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5b6b-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5b6b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5b6b-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="b5b6b-107">[in] Der Pfad der Datei, die untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="b5b6b-108">[in, out] Der Puffer zugeordnet werden, für die Versionsinformationen, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b5b6b-109">[in] Die Größe in Breitzeichen, der `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b5b6b-110">[out] Die Größe in Bytes, des zurückgegebenen `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b5b6b-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b6b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5b6b-111">Requirements</span></span>  
 <span data-ttu-id="b5b6b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5b6b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b6b-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5b6b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5b6b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5b6b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b6b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5b6b-115">See also</span></span>

- [<span data-ttu-id="b5b6b-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b5b6b-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
