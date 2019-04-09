---
title: ICLRStrongName::StrongNameGetPublicKey-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2acade14f9d30ca7bf0d098d6f58c80a367f621c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213011"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="f2209-102">ICLRStrongName::StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="f2209-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="f2209-103">Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar ab.</span><span class="sxs-lookup"><span data-stu-id="f2209-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="f2209-104">Das Schlüsselpaar kann entweder als einen Schlüsselcontainernamen in einen Kryptografiedienstanbieter (CSP) oder als unformatierte Bytes Auflistung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2209-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2209-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2209-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2209-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2209-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="f2209-107">[in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="f2209-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f2209-108">Wenn `pbKeyBlob` null ist, `szKeyContainer` müssen einen gültigen Container im CSP angeben.</span><span class="sxs-lookup"><span data-stu-id="f2209-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="f2209-109">In diesem Fall die [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) Methode extrahiert den öffentlichen Schlüssel aus dem Schlüsselpaar im Container gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f2209-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f2209-110">Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="f2209-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f2209-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="f2209-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f2209-112">Es werden keine anderen Arten von Schlüsseln zu diesem Zeitpunkt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2209-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f2209-113">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="f2209-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f2209-114">Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="f2209-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f2209-115">Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `szKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="f2209-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f2209-116">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f2209-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f2209-117">[out] Die zurückgegebene öffentliches Schlüssel-BLOB.</span><span class="sxs-lookup"><span data-stu-id="f2209-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f2209-118">Die `ppbPublicKeyBlob` Parameter von der common Language Runtime zugeordnet ist, und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2209-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f2209-119">Der Aufrufer muss den Arbeitsspeicher freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f2209-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f2209-120">[out] Die Größe des zurückgegebenen öffentliche Schlüssel-BLOB.</span><span class="sxs-lookup"><span data-stu-id="f2209-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2209-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2209-121">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f2209-122">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="f2209-122">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2209-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2209-123">Remarks</span></span>  
 <span data-ttu-id="f2209-124">Der öffentliche Schlüssel befindet sich einem [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="f2209-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2209-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2209-125">Requirements</span></span>  
 <span data-ttu-id="f2209-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2209-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2209-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f2209-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f2209-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2209-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2209-129">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f2209-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2209-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2209-130">See also</span></span>

- [<span data-ttu-id="f2209-131">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="f2209-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f2209-132">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="f2209-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="f2209-133">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2209-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
