---
title: StrongNameKeyGenEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2ed9ba4b580b8f64fc05dbb429742442a36acf5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757467"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="f6db8-102">StrongNameKeyGenEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="f6db8-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="f6db8-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.</span><span class="sxs-lookup"><span data-stu-id="f6db8-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="f6db8-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f6db8-104">This function has been deprecated.</span></span> <span data-ttu-id="f6db8-105">Verwenden der [ICLRStrongName:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="f6db8-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6db8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6db8-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6db8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6db8-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="f6db8-108">[in] Der angeforderte Schlüsselcontainer-Name.</span><span class="sxs-lookup"><span data-stu-id="f6db8-108">[in] The requested key container name.</span></span> <span data-ttu-id="f6db8-109">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f6db8-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f6db8-110">[in] Gibt an, ob den Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="f6db8-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="f6db8-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f6db8-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="f6db8-112">0 x 00000000 - wird verwendet, wenn `wszKeyContainer` null ist, um einen temporären Schlüsselcontainernamen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f6db8-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="f6db8-113">0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6db8-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="f6db8-114">[in] Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="f6db8-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="f6db8-115">[out] Das zurückgegebene öffentliches/privates Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="f6db8-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="f6db8-116">[out] Die Größe in Bytes, des `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f6db8-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6db8-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6db8-117">Return Value</span></span>  
 <span data-ttu-id="f6db8-118">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f6db8-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6db8-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6db8-119">Remarks</span></span>  
 <span data-ttu-id="f6db8-120">Die .NET Framework-Versionen 1.0 und 1.1 erfordert eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 bietet 2048-Bit-Schlüssel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6db8-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="f6db8-121">Nachdem der Schlüssel abgerufen werden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f6db8-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="f6db8-122">Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f6db8-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6db8-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6db8-123">Requirements</span></span>  
 <span data-ttu-id="f6db8-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6db8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6db8-125">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f6db8-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f6db8-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6db8-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6db8-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6db8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6db8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6db8-128">See also</span></span>

- [<span data-ttu-id="f6db8-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f6db8-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="f6db8-130">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="f6db8-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="f6db8-131">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6db8-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
