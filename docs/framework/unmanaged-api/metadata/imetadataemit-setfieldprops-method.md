---
title: IMetaDataEmit::SetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097654"
---
# <a name="imetadataemitsetfieldprops-method"></a>IMetaDataEmit::SetFieldProps-Methode
Legt fest oder aktualisiert den Standardwert für das Feld auf die durch das angegebene Feld-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fd`  
 [in] Das Token für das Feld "Ziel".  
  
 `dwFieldFlags`  
 [in] Feldattribute. Dies ist eine Bitmaske der `CorFieldAttr` Werte.  
  
 `dwCPlusTypeFlag`  
 [in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies ist eine `CorElementType` Wert. Wenn eine Konstante nicht definiert ist, legen Sie diesen Wert auf `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Der Konstante Wert für das Feld.  
  
 `cchValue`  
 [in] Die Größe in Unicode-Zeichen von `pValue`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
