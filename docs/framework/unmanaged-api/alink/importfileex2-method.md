---
title: ImportFileEx2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6584d31674670bcd005161a846b74df71a27a5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741648"
---
# <a name="importfileex2-method"></a>ImportFileEx2-Methode
Assemblys und ungebundenen Modulen importiert. Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber Sie funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFilename`  
 Name des zu importierenden Datei.  
  
 `pszTargetName`  
 Optionaler Name der Zieldatei.  
  
 `pAssemblyScopeIn`  
 Optionale importierte Bereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.  
  
 `fSmartImport`  
 True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.  
  
 `dwOpenFlags`  
 Flags, die zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Empfängt die eindeutige ID für die Assembly oder Datei.  
  
 `ppAssemblyScope`  
 Import Assemblybereich empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle. NULL kann sein, wenn die Datei keine Assembly ist.  
  
 `pdwCountOfScopes`  
 Empfängt die Anzahl der Dateien bzw. Bereiche nicht importiert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h an.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
