---
title: IMetaDataImport::GetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f8cccf8d583645982eb37f6afcb553914679ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075660"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="be1f5-102">IMetaDataImport::GetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="be1f5-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="be1f5-103">Ruft Metadaten ab, die dem Feld zugeordnet sind, auf das durch das angegebene FieldDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="be1f5-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be1f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be1f5-104">Syntax</span></span>  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be1f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be1f5-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="be1f5-106">[in] Ein FieldDef-Token, das Feld zum Abrufen der zugehörigen Metadaten für darstellt.</span><span class="sxs-lookup"><span data-stu-id="be1f5-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="be1f5-107">[out] Ein Zeiger auf ein TypeDef-Token, das den Typ der Klasse darstellt, das Feld gehört.</span><span class="sxs-lookup"><span data-stu-id="be1f5-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="be1f5-108">[out] Der Name des Felds.</span><span class="sxs-lookup"><span data-stu-id="be1f5-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="be1f5-109">[in] Die Größe in Zeichen des Puffers für *SzField*.</span><span class="sxs-lookup"><span data-stu-id="be1f5-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="be1f5-110">[out] Die tatsächliche Größe des zurückgegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="be1f5-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="be1f5-111">[out] Flags, die mit den Metadaten des Felds.</span><span class="sxs-lookup"><span data-stu-id="be1f5-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="be1f5-112">[in] Ein Zeiger auf die binäre Metadatenwert, der die Felder beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="be1f5-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="be1f5-113">[out] Die Größe in Bytes der `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="be1f5-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="be1f5-114">[out] Ein Flag, das den Wert des Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="be1f5-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="be1f5-115">[out] Ein konstanter Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="be1f5-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="be1f5-116">[out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn keine Zeichenfolge vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="be1f5-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be1f5-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be1f5-117">Requirements</span></span>  
 <span data-ttu-id="be1f5-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be1f5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be1f5-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be1f5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be1f5-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="be1f5-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be1f5-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be1f5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1f5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be1f5-122">See also</span></span>

- [<span data-ttu-id="be1f5-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be1f5-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="be1f5-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be1f5-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
