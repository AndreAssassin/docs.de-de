---
title: IMetaDataTables::GetNextUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ce6cfd6a331c9d9695f65eb3a670305de38d010
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779846"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="421e5-102">IMetaDataTables::GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="421e5-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="421e5-103">Ruft den Index der Zeile, die die nächste hartcodierten Zeichenfolge in der aktuellen Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="421e5-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="421e5-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="421e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="421e5-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="421e5-106">[in] Ein Indexwert aus der aktuellen Zeichenfolgenspalte.</span><span class="sxs-lookup"><span data-stu-id="421e5-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="421e5-107">[out] Ein Zeiger auf den Zeilenindex der nächsten Zeichenfolge in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="421e5-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="421e5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="421e5-108">Remarks</span></span>  
 <span data-ttu-id="421e5-109">Die Verwendung von dieser Methode wird nicht empfohlen, da es keine konsistente Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="421e5-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="421e5-110">Informationen über den GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="421e5-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="421e5-111">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="421e5-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421e5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="421e5-112">Requirements</span></span>  
 <span data-ttu-id="421e5-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421e5-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="421e5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="421e5-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="421e5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="421e5-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421e5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421e5-117">See also</span></span>

- [<span data-ttu-id="421e5-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="421e5-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="421e5-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="421e5-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
