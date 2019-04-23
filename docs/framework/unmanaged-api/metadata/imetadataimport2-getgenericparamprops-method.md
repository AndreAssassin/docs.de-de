---
title: IMetaDataImport2::GetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082333"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps-Methode
Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `gp`  
 [in] Das Token, das den generischen Parameter für die zurückzugebenden Metadaten darstellt.  
  
 `pulParamSeq`  
 [out] Die Ordnungsposition der `Type` Parameter in der übergeordneten Konstruktor oder die Methode.  
  
 `pdwParamFlags`  
 [out] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) Enumeration, die beschreibt die `Type` für den generischen Parameter.  
  
 `ptOwner`  
 [out] Eine TypeDef oder MethodDef-Token, das den Besitzer des Parameters darstellt.  
  
 `reserved`  
 [out] Reserviert für zukünftige Erweiterbarkeit.  
  
 `wzName`  
 [out] Der Name des generischen Parameters.  
  
 `cchName`  
 [in] Die Größe der `wzName` Puffer.  
  
 `pchName`  
 [out] Die zurückgegebene Größe mit dem Namen, in Breitzeichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
