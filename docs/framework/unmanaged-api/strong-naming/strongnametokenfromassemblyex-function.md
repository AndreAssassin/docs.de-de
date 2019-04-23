---
title: StrongNameTokenFromAssemblyEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95f00fea637b5263699779b7abe9863d266d7f19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099364"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="f2de4-102">StrongNameTokenFromAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="f2de4-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="f2de4-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel, den das Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="f2de4-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="f2de4-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f2de4-104">This function has been deprecated.</span></span> <span data-ttu-id="f2de4-105">Verwenden der [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="f2de4-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2de4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2de4-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2de4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2de4-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f2de4-108">[in] Der Pfad zu der PE (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="f2de4-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="f2de4-109">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="f2de4-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="f2de4-110">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="f2de4-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f2de4-111">[out] Der zurückgegebene öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f2de4-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f2de4-112">[out] Die Größe in Byte des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="f2de4-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2de4-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2de4-113">Return Value</span></span>  
 <span data-ttu-id="f2de4-114">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f2de4-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2de4-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2de4-115">Remarks</span></span>  
 <span data-ttu-id="f2de4-116">Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f2de4-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="f2de4-117">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f2de4-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="f2de4-118">Das Token ist ein Bestandteil des starken Namens für die Assembly, und Sie können aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="f2de4-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="f2de4-119">Nachdem der Schlüssel wird abgerufen, und das Token erstellt wird, sollten Sie rufen die [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f2de4-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="f2de4-120">Wenn die `StrongNameTokenFromAssemblyEx` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f2de4-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2de4-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2de4-121">Requirements</span></span>  
 <span data-ttu-id="f2de4-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2de4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2de4-123">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f2de4-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f2de4-124">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2de4-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="f2de4-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2de4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2de4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2de4-126">See also</span></span>

- [<span data-ttu-id="f2de4-127">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f2de4-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="f2de4-128">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f2de4-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="f2de4-129">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2de4-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
