---
title: INotifySink2::OnSyncCallOut-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf36b9e09f5e9eeb28930a6adc48426927a60e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940360"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="4db73-102">INotifySink2::OnSyncCallOut-Methode</span><span class="sxs-lookup"><span data-stu-id="4db73-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="4db73-103">Wird aufgerufen, wenn ein Aufruf ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4db73-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4db73-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4db73-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4db73-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="4db73-106">[in] Die ID des Aufrufs, der ausgegeben wurde. Finden Sie unter [CALL_ID-Struktur](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="4db73-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="4db73-107">[out] Rufen Sie die Puffer.</span><span class="sxs-lookup"><span data-stu-id="4db73-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="4db73-108">[out] Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4db73-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4db73-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4db73-109">Return Value</span></span>  
 <span data-ttu-id="4db73-110">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4db73-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db73-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4db73-111">Requirements</span></span>  
 <span data-ttu-id="4db73-112">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="4db73-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db73-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db73-113">See also</span></span>

- [<span data-ttu-id="4db73-114">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4db73-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="4db73-115">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4db73-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="4db73-116">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4db73-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
