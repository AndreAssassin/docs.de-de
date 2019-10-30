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
ms.openlocfilehash: d5e7841844c8fa500935eb9cba06f4e2fe95d2d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111995"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="83281-102">ICLRDataTarget3::GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="83281-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="83281-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="83281-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="83281-104">Bei einem dumpziel wäre dies z. b. äquivalent zu dem Ausnahme Daten Satz, der über das `ExceptionParam`-Argument an die [minidumpschreitedump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows-Debug-Hilfe-Bibliothek (dbghelp) weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="83281-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83281-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83281-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83281-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="83281-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="83281-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="83281-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="83281-108">Dieser muss gleich `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`sein.</span><span class="sxs-lookup"><span data-stu-id="83281-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="83281-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="83281-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="83281-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Ausnahmedatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="83281-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="83281-111">Der Ausnahme Daten Satz wird als [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) -Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="83281-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83281-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83281-112">Return Value</span></span>  
 <span data-ttu-id="83281-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="83281-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="83281-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="83281-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="83281-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="83281-115">Return code</span></span>|<span data-ttu-id="83281-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83281-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="83281-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="83281-117">Method succeeded.</span></span> <span data-ttu-id="83281-118">Der Ausnahmedatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="83281-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="83281-119">Kein Ausnahmedatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="83281-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="83281-120">Die Eingabepuffergröße ist ungleich `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="83281-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83281-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83281-121">Remarks</span></span>  
 <span data-ttu-id="83281-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) ist eine Struktur, die in "dbghelp. h" und "Imagehlp. h" in der Windows SDK definiert ist.</span><span class="sxs-lookup"><span data-stu-id="83281-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="83281-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="83281-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83281-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83281-124">Requirements</span></span>  
 <span data-ttu-id="83281-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83281-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83281-126">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="83281-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="83281-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83281-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83281-128">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83281-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83281-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83281-129">See also</span></span>

- [<span data-ttu-id="83281-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83281-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="83281-131">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="83281-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="83281-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="83281-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
