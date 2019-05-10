---
title: CertVerifyAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06f69bf867b565edbab06dadb32e5377357e91f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617704"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="dccd2-102">CertVerifyAuthenticodeLicense-Funktion</span><span class="sxs-lookup"><span data-stu-id="dccd2-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="dccd2-103">Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="dccd2-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dccd2-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dccd2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dccd2-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="dccd2-106">[in] Die Authenticode-XrML-Lizenz, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="dccd2-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="dccd2-107">Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.</span><span class="sxs-lookup"><span data-stu-id="dccd2-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dccd2-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="dccd2-108">[in] Optional.</span></span> <span data-ttu-id="dccd2-109">Eine Kombination der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="dccd2-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="dccd2-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="dccd2-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="dccd2-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="dccd2-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="dccd2-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="dccd2-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="dccd2-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="dccd2-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="dccd2-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="dccd2-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="dccd2-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="dccd2-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="dccd2-116">[out] Für den Erhalt von Informationen über den Signaturgeber.</span><span class="sxs-lookup"><span data-stu-id="dccd2-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="dccd2-117">Wenn die Lizenz nicht signiert wurde, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt.</span><span class="sxs-lookup"><span data-stu-id="dccd2-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="dccd2-118">Es ist der Verantwortung des Aufrufers, Ressourcen freizugeben, mit der [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) Funktion nach der Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dccd2-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="dccd2-119">Finden Sie unter [AXL_AUTHENTICODE_SIGNER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="dccd2-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="dccd2-120">[out] Für den Erhalt von Informationen über den Ersteller des Zeitstempels, wenn verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dccd2-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="dccd2-121">Wenn die Lizenz keinen Zeitstempel erhalten hat, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt.</span><span class="sxs-lookup"><span data-stu-id="dccd2-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="dccd2-122">Es ist der Verantwortung des Aufrufers, Ressourcen freizugeben, mit der [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) Funktion nach der Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dccd2-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="dccd2-123">Finden Sie unter [AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="dccd2-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dccd2-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dccd2-124">Return Value</span></span>  
 <span data-ttu-id="dccd2-125">Gibt bei Erfolg `S_OK` zurück.</span><span class="sxs-lookup"><span data-stu-id="dccd2-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="dccd2-126">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dccd2-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccd2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dccd2-127">See also</span></span>

- [<span data-ttu-id="dccd2-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="dccd2-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [<span data-ttu-id="dccd2-129">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="dccd2-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="dccd2-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dccd2-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
