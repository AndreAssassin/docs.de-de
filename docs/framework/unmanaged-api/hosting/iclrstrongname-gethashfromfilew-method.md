---
title: ICLRStrongName::GetHashFromFileW-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 553acc178bc5805b5afef5931fefc8ad74cbac39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135176"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="8f17a-102">ICLRStrongName::GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="8f17a-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="8f17a-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="8f17a-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f17a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f17a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8f17a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f17a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8f17a-106">in Der Unicode-Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="8f17a-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8f17a-107">[in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f17a-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="8f17a-108">Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8f17a-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="8f17a-109">Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f17a-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8f17a-110">vorgenommen Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="8f17a-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8f17a-111">in Die maximale Größe des Puffers, auf den `pbHash`zeigt.</span><span class="sxs-lookup"><span data-stu-id="8f17a-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8f17a-112">vorgenommen Die Größe `pbHash`in Byte.</span><span class="sxs-lookup"><span data-stu-id="8f17a-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f17a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f17a-113">Return Value</span></span>  
 <span data-ttu-id="8f17a-114">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="8f17a-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f17a-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f17a-115">Remarks</span></span>  
 <span data-ttu-id="8f17a-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) -Methode, mit der Ausnahme, dass die Dateinamen Spezifikation anstelle von ANSI Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="8f17a-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f17a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f17a-117">Requirements</span></span>  
 <span data-ttu-id="8f17a-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f17a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f17a-119">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="8f17a-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8f17a-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f17a-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f17a-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f17a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f17a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f17a-122">See also</span></span>

- [<span data-ttu-id="8f17a-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="8f17a-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="8f17a-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f17a-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
