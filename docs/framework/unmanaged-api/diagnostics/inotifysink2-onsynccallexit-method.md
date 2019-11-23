---
title: INotifySink2::OnSyncCallExit-Methode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: 03b8afc1276dae6244bcf12bd0bc78c2fa5380bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448681"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="a13e9-102">INotifySink2::OnSyncCallExit-Methode</span><span class="sxs-lookup"><span data-stu-id="a13e9-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="a13e9-103">Gets invoked when exiting a call.</span><span class="sxs-lookup"><span data-stu-id="a13e9-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a13e9-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a13e9-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="a13e9-106">[in] ID of the call being exited.</span><span class="sxs-lookup"><span data-stu-id="a13e9-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="a13e9-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="a13e9-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="a13e9-108">[out] Call buffer.</span><span class="sxs-lookup"><span data-stu-id="a13e9-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="a13e9-109">[out] Size of the call buffer, in bytes.</span><span class="sxs-lookup"><span data-stu-id="a13e9-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a13e9-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a13e9-110">Return Value</span></span>  
 <span data-ttu-id="a13e9-111">S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="a13e9-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13e9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a13e9-112">Requirements</span></span>  
 <span data-ttu-id="a13e9-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a13e9-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13e9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a13e9-114">See also</span></span>

- [<span data-ttu-id="a13e9-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a13e9-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="a13e9-116">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a13e9-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="a13e9-117">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a13e9-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
