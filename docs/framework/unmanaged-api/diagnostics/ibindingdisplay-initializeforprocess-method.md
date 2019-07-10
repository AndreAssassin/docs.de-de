---
title: IBindingDisplay::InitializeForProcess-Methode
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775947"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="f8868-102">IBindingDisplay::InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f8868-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="f8868-103">Initialisiert die [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="f8868-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8868-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8868-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8868-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8868-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="f8868-106">[in] Die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="f8868-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8868-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8868-107">Remarks</span></span>  
 <span data-ttu-id="f8868-108">Der Debugger Ruft die `InitializeForProcess` Methode zum Zeitpunkt der Erstellung die Bindungsanzeige zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f8868-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="f8868-109">`InitializeForProcess` muss zum Zeitpunkt der Erstellung vor jeder anderen Methode aufgerufen werden, für `IBindingDisplay` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f8868-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8868-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8868-110">Requirements</span></span>  
 <span data-ttu-id="f8868-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8868-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8868-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="f8868-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="f8868-113">**Bibliothek:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="f8868-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="f8868-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8868-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8868-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8868-115">See also</span></span>

- [<span data-ttu-id="f8868-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8868-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
