---
title: ICorDebugSymbolProvider2::GetFrameProps-Methode
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 274da030bbbb7c614709b5150f08f37ddf5aaf5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771160"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a>ICorDebugSymbolProvider2::GetFrameProps-Methode
Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `codeRva`  
 [in] Eine coderelative virtuelle Adresse.  
  
 `pCodeStartRva`  
 [out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.  
  
 `pParentFrameStartRva`  
 [out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
