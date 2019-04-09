---
title: ICLRDataTarget3::GetExceptionRecord-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7966cfb6e775bee567221eef2a5d99b90399f322
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140841"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>ICLRDataTarget3::GetExceptionRecord-Methode
Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist. Z. B. bei einem Sicherungsziel entspräche dem Ausnahmedatensatz, der über übergeben die `ExceptionParam` Argument für die [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows Debug-Hilfe-Bibliothek (DbgHelp).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bufferSize`  
 [in] Die Eingabepuffergröße, in Bytes. Dies muss gleich sein `sizeof(` [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.  
  
 `bufferUsed`  
 [out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.  
  
 `buffer`  
 [out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Ausnahmedatensatzes empfängt. Der Ausnahmedatensatz wird zurückgegeben, als eine [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Der Ausnahmedatensatz ist in den Ausgabepuffer kopiert worden.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Kein Ausnahmedatensatz ist dem Ziel zugeordnet.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Die Eingabepuffergröße ist ungleich `sizeof(MINIDUMP_EXCEPTION)`.|  
  
## <a name="remarks"></a>Hinweise  
 [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) ist eine Struktur, die in dbghelp.h "und" imagehlp.h im Windows SDK definiert wird.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionContextRecord-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [GetExceptionThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
