---
title: IMetaDataImport::GetEventProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c87f2212c761dc31a75addabca6970c5497aa2a0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782426"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps-Methode
Ruft Metadateninformationen für das Ereignis durch, einschließlich der deklarierende Typ, hinzufügen und Entfernungsmethoden für Delegaten, und alle Flags und sonstigen zugeordneten Daten das angegebene Ereignistoken dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ev`  
 [in] Das Ereignis-Metadatentoken, das das Ereignis, das Abrufen von Metadaten für darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, die die Klasse darstellt, die das Ereignis deklariert.  
  
 `szEvent`  
 [out] Der Name des Ereignisses verweist `ev`.  
  
 `pchEvent`  
 [in] Die angeforderte Länge in Breitzeichen `szEvent`.  
  
 `pdwEventFlags`  
 [out] Die zurückgegebene Länge in Breitzeichen `szEvent`.  
  
 `ptkEventType`  
 [out] Ein Zeiger auf ein TypeRef oder TypeDef Metadaten token, die <xref:System.Delegate> der Ereignistyp.  
  
 `pmdAddOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode, die fügt Handler für das Ereignis darstellt.  
  
 `pmdRemoveOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode, die Handler für das Ereignis entfernt darstellt.  
  
 `pmdFire`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode, die das Ereignis auslöst darstellt.  
  
 `rmdOtherMethod`  
 [out] Ein Array von Sicherheitstoken Verweise auf andere Methoden, die dem Ereignis zugeordnet werden soll.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der in zurückgegebenen Token `rmdOtherMethod`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
