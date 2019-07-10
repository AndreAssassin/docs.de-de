---
title: ICLRStrongName::StrongNameSignatureSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8bf6d69f8490f05532df3e164107760c2b574e2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755016"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="a1332-102">ICLRStrongName::StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a1332-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="a1332-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="a1332-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="a1332-104">Diese Methode wird in der Regel vom Compiler verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert, beim Erstellen einer mit Verzögerung signierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="a1332-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1332-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1332-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a1332-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1332-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="a1332-107">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="a1332-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="a1332-108">[in] Die Größe in Bytes, des `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a1332-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="a1332-109">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1332-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1332-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1332-110">Return Value</span></span>  
 <span data-ttu-id="a1332-111">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="a1332-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1332-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1332-112">Requirements</span></span>  
 <span data-ttu-id="a1332-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1332-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1332-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a1332-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a1332-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a1332-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1332-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1332-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1332-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1332-117">See also</span></span>

- [<span data-ttu-id="a1332-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1332-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
