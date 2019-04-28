---
title: IMetaDataImport::GetUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 358346af540c8b6b7ee1523e763bebbacf8cd2bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777519"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="2aa92-102">IMetaDataImport::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="2aa92-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="2aa92-103">Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2aa92-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2aa92-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aa92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2aa92-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="2aa92-106">[in] Das Zeichenfolgentoken, das an die zugeordnete Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2aa92-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="2aa92-107">[out] Eine Kopie der angeforderten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2aa92-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="2aa92-108">[in] Die maximale Größe in Breitzeichen des angeforderten `szString`.</span><span class="sxs-lookup"><span data-stu-id="2aa92-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="2aa92-109">[out] Die Größe in Breitzeichen des zurückgegebenen `szString`.</span><span class="sxs-lookup"><span data-stu-id="2aa92-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa92-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2aa92-110">Requirements</span></span>  
 <span data-ttu-id="2aa92-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aa92-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa92-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2aa92-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2aa92-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2aa92-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2aa92-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa92-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa92-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa92-115">See also</span></span>

- [<span data-ttu-id="2aa92-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2aa92-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2aa92-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2aa92-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
