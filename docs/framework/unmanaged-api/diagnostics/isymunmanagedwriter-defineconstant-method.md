---
title: ISymUnmanagedWriter::DefineConstant-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f470dbe4ef2ef0d5f2204ccbdd5fb64730f9a2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930103"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a>ISymUnmanagedWriter::DefineConstant-Methode
Definiert einen Namen für einen konstanten Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 [in] Ein Zeiger auf eine `WCHAR` , die den Namen den Konstanten definiert.  
  
 `value`  
 [in] Der Wert der Konstanten.  
  
 `cSig`  
 [in] Die Größe des `signature`-Arrays.  
  
 `signature`  
 [in] Die Typsignatur für die Konstante.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [DefineConstant2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
