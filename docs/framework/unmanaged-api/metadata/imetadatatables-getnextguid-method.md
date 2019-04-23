---
title: IMetaDataTables::GetNextGuid-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110468"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="031ca-102">IMetaDataTables::GetNextGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="031ca-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="031ca-103">Ruft den Index der nächsten GUID-Wert in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="031ca-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="031ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="031ca-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="031ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="031ca-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="031ca-106">[in] Der Indexwert aus der eine GUID-Spalte.</span><span class="sxs-lookup"><span data-stu-id="031ca-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="031ca-107">[out] Ein Zeiger auf den Index des nächsten GUID-Werts.</span><span class="sxs-lookup"><span data-stu-id="031ca-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="031ca-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="031ca-108">Remarks</span></span>  
 <span data-ttu-id="031ca-109">Die Verwendung von dieser Methode wird nicht empfohlen, da es keine konsistente Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="031ca-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="031ca-110">Informationen über den GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="031ca-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="031ca-111">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="031ca-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="031ca-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="031ca-112">Requirements</span></span>  
 <span data-ttu-id="031ca-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="031ca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031ca-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="031ca-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="031ca-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="031ca-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="031ca-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="031ca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031ca-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="031ca-117">See also</span></span>

- [<span data-ttu-id="031ca-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="031ca-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="031ca-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="031ca-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
