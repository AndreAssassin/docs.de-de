---
title: IMetaDataTables::GetTableInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82c88c75d5799134d8c683c91e28f956743b84ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194512"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="e0c0f-102">IMetaDataTables::GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e0c0f-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="e0c0f-103">Ruft ab, Name, Größe, Anzahl der Zeilen, die Anzahl der Spalten und Schlüsselspaltenindex der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0c0f-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c0f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0c0f-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="e0c0f-106">[in] Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="e0c0f-107">[out] Ein Zeiger auf die Größe in Bytes, der eine Zeile einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="e0c0f-108">[out] Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="e0c0f-109">[out] Ein Zeiger auf die Anzahl der Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="e0c0f-110">[out] Ein Zeiger auf den Index der Spalte für den Schlüssel oder -1, wenn die Tabelle keine Schlüsselspalte.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="e0c0f-111">[out] Ein Zeiger auf einen Zeiger auf den Namen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0c0f-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c0f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0c0f-112">Requirements</span></span>  
 <span data-ttu-id="e0c0f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c0f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c0f-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0c0f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0c0f-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e0c0f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e0c0f-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e0c0f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0c0f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0c0f-117">See also</span></span>

- [<span data-ttu-id="e0c0f-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c0f-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="e0c0f-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c0f-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
