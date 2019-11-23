---
title: ISymUnmanagedVariable::GetAttributes-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: cfc28dfcda7bf4b3d1fc6fe3530a212ee76fadd2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446085"
---
# <a name="isymunmanagedvariablegetattributes-method"></a>ISymUnmanagedVariable::GetAttributes-Methode
Gets the attribute flags for this variable.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] A pointer to a `ULONG32` that receives the attributes. The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK if the method succeeds; otherwise, E_FAIL or some other error code.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
