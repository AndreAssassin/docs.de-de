---
title: ICLRStrongName::GetHashFromAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 714827da24b3fc0a334210fd94e61f80cb2afe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993108"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="37474-102">ICLRStrongName::GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="37474-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="37474-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="37474-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37474-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37474-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37474-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37474-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="37474-106">[in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="37474-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="37474-107">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="37474-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="37474-108">Verwenden Sie 0 (null), für den Standard-Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="37474-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="37474-109">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="37474-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="37474-110">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="37474-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="37474-111">[out] Die zurückgegebene Größe in Bytes, `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="37474-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37474-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37474-112">Return Value</span></span>  
 <span data-ttu-id="37474-113">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="37474-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37474-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37474-114">Requirements</span></span>  
 <span data-ttu-id="37474-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37474-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37474-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="37474-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="37474-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="37474-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37474-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37474-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37474-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37474-119">See also</span></span>

- [<span data-ttu-id="37474-120">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="37474-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="37474-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37474-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
