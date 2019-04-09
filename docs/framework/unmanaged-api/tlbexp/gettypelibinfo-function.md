---
title: GetTypeLibInfo-Funktion
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148537"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo-Funktion
Gibt Informationen über die angegebene Typbibliothek durch Untersuchen der [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szFile`  
 [in] Der Dateiname der Typbibliothek.  
  
 `pTypeLibID`  
 [out] Die GUID der Typbibliothek.  
  
 `pTypeLibLCID`  
 [out] Die Lokalisierungs-ID der Typbibliothek.  
  
 `pTypeLibPlatform`  
 [out] Ein [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) Flag, das das Zielbetriebssystem für die Typbibliothek identifiziert. Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Die Hauptversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.  
  
 `pTypeLibMinorVer`  
 [out] Die Nebenversionsnummer der Typbibliothek. Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetTypeLibInfo` Funktion wird aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Dieses Tool generiert eine Typbibliothek, die die Typen in einer Assembly der common Language Runtime (CLR) beschreibt.  
  
 Wenn alle Parameter null ist, gibt die Funktion eine `HRESULT` von `E_POINTER`. Andernfalls wird `S_OK`zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** TlbRef.h  
  
 **Bibliothek:** TlbRef.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Tlbexp-Hilfsfunktionen](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
