---
title: ICeeGen::GetString-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70d78942d4db2fea2cc1ccbcc5ddb20d743e9fdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093669"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="1b830-102">ICeeGen::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="1b830-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="1b830-103">Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1b830-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="1b830-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b830-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b830-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b830-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b830-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b830-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="1b830-107">[in] Die relative virtuelle Adresse der Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b830-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="1b830-108">[out] Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1b830-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b830-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b830-109">Requirements</span></span>  
 <span data-ttu-id="1b830-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b830-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b830-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1b830-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b830-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1b830-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b830-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b830-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b830-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b830-114">See also</span></span>

- [<span data-ttu-id="1b830-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b830-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
