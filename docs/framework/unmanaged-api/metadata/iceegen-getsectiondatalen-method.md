---
title: ICeeGen::GetSectionDataLen-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198711"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="9d9c1-102">ICeeGen::GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="9d9c1-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="9d9c1-103">Ruft die Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="9d9c1-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="9d9c1-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d9c1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d9c1-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d9c1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d9c1-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9d9c1-107">[in] Der Datenabschnitt, deren Länge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9d9c1-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="9d9c1-108">[out] Die zurückgegebene Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="9d9c1-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d9c1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d9c1-109">Remarks</span></span>  
 <span data-ttu-id="9d9c1-110">Rufen Sie `GetSectionDataLen` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9d9c1-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d9c1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d9c1-111">Requirements</span></span>  
 <span data-ttu-id="9d9c1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d9c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d9c1-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d9c1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d9c1-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9d9c1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d9c1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d9c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9c1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d9c1-116">See also</span></span>

- [<span data-ttu-id="9d9c1-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d9c1-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
