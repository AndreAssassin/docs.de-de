---
title: IMetaDataImport::FindMethod-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4225794740b7786c6f758c9a0953d323c31a1081
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782487"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod-Methode
Ruft einen Zeiger auf das MethodDef token für die Methode, die eingeschlossen ist mit dem angegebenen <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Die `mdTypeDef` token für den Typ (eine Klasse oder Schnittstelle), der zu suchenden Members einschließt. Wenn dieser Wert ist `mdTokenNil`, und klicken Sie dann die Suche für eine globale Funktion durchgeführt wird.  
  
 `szName`  
 [in] Der Name der zu suchenden Methode.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes der `pvSigBlob`.  
  
 `pmb`  
 [out] Ein Zeiger auf das entsprechende MethodDef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie die Methode, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`). Es gibt möglicherweise mehrere Methoden mit demselben Namen in einer Klasse oder Schnittstelle. In diesem Fall übergeben Sie der Methodensignatur, um die eindeutige Übereinstimmung zu finden.  
  
 Die Signatur, die an `FindMethod` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind. Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert. Das Token ist ein Index in die lokale TypeDef-Tabelle. Sie erstellen eine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMethod`.  
  
 `FindMethod` Sucht nur die Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
