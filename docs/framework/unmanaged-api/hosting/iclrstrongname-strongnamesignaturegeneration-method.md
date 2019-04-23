---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165780"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="81acc-102">ICLRStrongName::StrongNameSignatureGeneration-Methode</span><span class="sxs-lookup"><span data-stu-id="81acc-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="81acc-103">Generiert eine Signatur mit starkem Namen für die angegebene Assembly.</span><span class="sxs-lookup"><span data-stu-id="81acc-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81acc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81acc-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81acc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81acc-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="81acc-106">[in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur mit starkem Namen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="81acc-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="81acc-107">[in] Der Name des Schlüsselcontainers, die das öffentlich/privat-Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="81acc-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="81acc-108">Wenn `pbKeyBlob` null ist, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben.</span><span class="sxs-lookup"><span data-stu-id="81acc-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="81acc-109">In diesem Fall dient das Schlüsselpaar im Container gespeicherten zum Signieren der Datei.</span><span class="sxs-lookup"><span data-stu-id="81acc-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="81acc-110">Wenn `pbKeyBlob` ist nicht null ist, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="81acc-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="81acc-111">Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein.</span><span class="sxs-lookup"><span data-stu-id="81acc-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="81acc-112">Es werden keine anderen Arten von Schlüsseln zu diesem Zeitpunkt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81acc-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="81acc-113">[in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="81acc-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="81acc-114">Dieses Paar hat das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion.</span><span class="sxs-lookup"><span data-stu-id="81acc-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="81acc-115">Wenn `pbKeyBlob` null festgelegt ist, die mit angegebenen Container `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="81acc-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="81acc-116">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="81acc-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="81acc-117">[out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="81acc-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="81acc-118">Wenn `ppbSignatureBlob` ist null, die Laufzeit speichert-die Signatur in der Datei, die anhand des `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="81acc-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="81acc-119">Wenn `ppbSignatureBlob` ist nicht null ist, belegt die common Language Runtime Speicherplatz in dem die Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="81acc-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="81acc-120">Der Aufrufer muss diesen Speicherplatz freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="81acc-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="81acc-121">[out] Die Größe in Bytes der zurückgegebenen Signatur.</span><span class="sxs-lookup"><span data-stu-id="81acc-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81acc-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81acc-122">Return Value</span></span>  
 <span data-ttu-id="81acc-123">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="81acc-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81acc-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81acc-124">Remarks</span></span>  
 <span data-ttu-id="81acc-125">Geben Sie null für `wszFilePath` um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="81acc-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="81acc-126">Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81acc-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81acc-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81acc-127">Requirements</span></span>  
 <span data-ttu-id="81acc-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81acc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81acc-129">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="81acc-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="81acc-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="81acc-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81acc-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81acc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81acc-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81acc-132">See also</span></span>

- [<span data-ttu-id="81acc-133">StrongNameSignatureGenerationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="81acc-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="81acc-134">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81acc-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
