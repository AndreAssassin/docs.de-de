---
title: ISymUnmanagedDocument::GetLanguageVendor-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939827"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a>ISymUnmanagedDocument::GetLanguageVendor-Methode
Ruft den Compilerhersteller des in diesem Dokument ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Ein Zeiger auf eine Variable, die den Compilerhersteller empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
