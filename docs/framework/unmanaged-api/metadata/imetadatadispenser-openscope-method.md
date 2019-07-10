---
title: IMetaDataDispenser::OpenScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e157c758b472ea89e21c1ed1ba8c17693c20a3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777794"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope-Methode
Öffnet eine vorhandene, auf dem Datenträger-Datei, und seine Metadaten in den Arbeitsspeicher zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szScope`  
 [in] Der Name der Datei, die geöffnet werden. Die Datei muss die common Language Runtime (CLR)-Metadaten enthalten.  
  
 `dwOpenFlags`  
 [in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) Enumeration, den Modus (Lesen, schreiben und so weiter) zum Öffnen.  
  
 `riid`  
 [in] Die IID der Metadatenschnittstelle gewünschten zurückgegeben werden; der Aufrufer verwendet die Schnittstelle zum Importieren von (Lesen), oder (Schreiben)-Metadaten ausgeben.  
  
 Der Wert des `riid` müssen eine der Schnittstellen "Import" oder "Ausgabe" angeben. Gültige Werte sind IID_IMetaDataEmit IID_IMetaDataImport auf, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [out] Der Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die in-Memory-Kopie der Metadaten kann abgefragt werden, mithilfe der Methoden aus einer der Schnittstellen "Import" oder mit Methoden, von dem der Schnittstellen "Ausgabe" hinzugefügt.  
  
 Wenn die Zieldatei keine CLR-Metadaten, die `OpenScope` Methode fehl.  
  
 In .NET Framework, Version 1.0 und Version 1.1, wenn ein Bereich wird mit geöffnet `dwOpenFlags` auf festgelegt, ist es für die Freigabe berechtigt. D.h., wenn nachfolgende Aufrufe von `OpenScope` übergeben Sie den Namen einer Datei, die zuvor schon geöffnet war, wird der vorhandene Bereich wiederverwendet und ein neuer Satz von Datenstrukturen nicht erstellt. Allerdings können Probleme aufgrund dieser Freigabe auftreten.  
  
 In .NET Framework, Version 2.0, Bereiche, die mit geöffnet `dwOpenFlags` Satz auf werden nicht mehr gemeinsam genutzt. Verwenden Sie den OfReadOnly-Wert, den Bereich freigegeben werden können. Abfragen, die verwenden "Metadatenschnittstellen Schreib-/" schlägt fehl, wenn ein Bereich freigegeben wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
