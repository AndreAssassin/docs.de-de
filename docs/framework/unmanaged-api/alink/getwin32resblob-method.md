---
title: GetWin32ResBlob-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4c77ade46d2401e2499a94504808efd94f79f93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152151"
---
# <a name="getwin32resblob-method"></a>GetWin32ResBlob-Methode
Ruft die Win32-Ressourcen-Blob ab. Rufen Sie diese Methode nach dem Festlegen von Assemblyoptionen für die an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
 `FileToken`  
 Datei-Token verwendet, um den Namen der Datei, die beim Erstellen der Versionsressource der Win32-verwendet werden  
  
 `fDll`  
 TRUE, wenn die Datei eine DLL, eine EXE-Datei "false" ist.  
  
 `pszIconFile`  
 Symbol "optional" zum Einfügen in das Ressourcen-Blob.  
  
 `ppResBlob`  
 Empfängt die Ressourcen-Blob.  
  
 `pcbResBlob`  
 Empfängt die Größe des BLOBs.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
