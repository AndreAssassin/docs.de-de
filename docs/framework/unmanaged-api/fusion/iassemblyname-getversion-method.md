---
title: IAssemblyName::GetVersion-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
ms.openlocfilehash: c0a43dc1640bdaa0ae104832eb4d1f8eb15b0392
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134336"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="3b161-102">IAssemblyName::GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="3b161-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="3b161-103">Ruft die Versionsinformationen für die Assembly ab, auf die von diesem [IAssemblyName](iassemblyname-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3b161-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b161-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b161-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b161-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b161-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="3b161-106">vorgenommen Die hohen 32 Bits der Version.</span><span class="sxs-lookup"><span data-stu-id="3b161-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="3b161-107">vorgenommen Die unteren 32 Bits der Version.</span><span class="sxs-lookup"><span data-stu-id="3b161-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b161-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b161-108">Requirements</span></span>  
 <span data-ttu-id="3b161-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b161-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b161-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3b161-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3b161-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b161-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b161-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b161-112">See also</span></span>

- [<span data-ttu-id="3b161-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b161-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
