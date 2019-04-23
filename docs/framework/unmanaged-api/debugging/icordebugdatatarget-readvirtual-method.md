---
title: ICorDebugDataTarget::ReadVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111526"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual-Methode
Ruft einen Block zusammenhängender Arbeitsspeicher, die beginnend ab der angegebenen Adresse, und der angegebene Puffer zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Die Startadresse des angeforderten Arbeitsspeichers.  
  
 `pbuffer`  
 [out] Der Puffer, in dem der Arbeitsspeicher gespeichert werden.  
  
 `bytesRequested`  
 [in] Die Anzahl der Bytes, die von der Zieladresse zu erhalten.  
  
 `pBytesRead`  
 [out] Die Anzahl der gelesenen Bytes tatsächlich von der Zieladresse. Dies kann weniger als sein `bytesRequested`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das erste Byte (an der angegebenen Adresse) gelesen werden kann, sollte der Aufruf erfolgreich (um das effiziente Lesen von Datenstrukturen mit selbstbeschreibend Länge haben, wie Null-terminierte Zeichenfolgen zu unterstützen) zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
