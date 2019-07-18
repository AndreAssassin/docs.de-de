---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8dd1daf3528bbc642033e254a809c18c3662ff1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779184"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps-Methode
Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadaten-Signatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdct`  
 [in] Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.  
  
 `szName`  
 [out] Der Name des exportierten Typs.  
  
 `cchName`  
 [in] Die Größe in Breitzeichen, der `szName`.  
  
 `pchName`  
 [out] Die Anzahl der Breitzeichen, die tatsächlich zurückgegeben. `szName`  
  
 `ptkImplementation`  
 [out] Ein `mdFile`, `mdAssemblyRef`, oder `mdExportedType` Metadatentoken, das enthält oder erlaubt den Zugriff auf die Eigenschaften des exportierten Typs.  
  
 `ptkTypeDef`  
 [out] Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.  
  
 `pdwExportedTypeFlags`  
 [out] Ein Zeiger auf die Flags, die in den exportierten Typ angewendete Metadaten beschreiben. Der Wert des Flags kann sein, eine oder mehrere [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Werte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
