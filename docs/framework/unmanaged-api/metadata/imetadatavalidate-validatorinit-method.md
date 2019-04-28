---
title: IMetaDataValidate::ValidatorInit-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31ff2c62810061cd8b774e934167a5ee3acf040c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645080"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="59274-102">IMetaDataValidate::ValidatorInit-Methode</span><span class="sxs-lookup"><span data-stu-id="59274-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="59274-103">Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Überprüfungsfehler.</span><span class="sxs-lookup"><span data-stu-id="59274-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59274-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59274-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59274-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="59274-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="59274-106">[in] Der Wert der [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="59274-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="59274-107">[in] Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Instanz, die als Funktionsrückruf für Validierungsfehler dient.</span><span class="sxs-lookup"><span data-stu-id="59274-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59274-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59274-108">Requirements</span></span>  
 <span data-ttu-id="59274-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59274-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59274-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="59274-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59274-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="59274-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59274-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59274-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59274-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59274-113">See also</span></span>

- [<span data-ttu-id="59274-114">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="59274-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
