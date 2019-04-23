---
title: INotifySink2::OnSyncCallReturn-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0adc6ec1db3f12d1850bb6ff9a01d5b6cc5f90c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157923"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="720ba-102">INotifySink2::OnSyncCallReturn-Methode</span><span class="sxs-lookup"><span data-stu-id="720ba-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="720ba-103">Wird aufgerufen, wenn ein Aufruf zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="720ba-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="720ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="720ba-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="720ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="720ba-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="720ba-106">[in] Die ID des Aufrufs von zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="720ba-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="720ba-107">Finden Sie unter [CALL_ID-Struktur](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="720ba-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="720ba-108">[in] Rufen Sie die Puffer.</span><span class="sxs-lookup"><span data-stu-id="720ba-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="720ba-109">[in] Größe des Aufrufpuffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="720ba-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="720ba-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="720ba-110">Return Value</span></span>  
 <span data-ttu-id="720ba-111">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="720ba-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="720ba-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="720ba-112">Requirements</span></span>  
 <span data-ttu-id="720ba-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="720ba-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="720ba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="720ba-114">See also</span></span>

- [<span data-ttu-id="720ba-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="720ba-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="720ba-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="720ba-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="720ba-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="720ba-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
