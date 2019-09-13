---
title: ICorDebugModule::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7f62385031967c164915fd31735a6d962f557fa
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894991"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="4c904-102">ICorDebugModule::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="4c904-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="4c904-103">Ruft den Dateinamen des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="4c904-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c904-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c904-104">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c904-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c904-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="4c904-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="4c904-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4c904-107">in Ein Zeiger auf die Länge des zurückgegebenen Namens.</span><span class="sxs-lookup"><span data-stu-id="4c904-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="4c904-108">vorgenommen Ein Array, in dem der zurückgegebene Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4c904-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c904-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c904-109">Remarks</span></span>  
 <span data-ttu-id="4c904-110">Die `GetName` -Methode gibt ein S_OK HRESULT zurück, wenn der Dateiname des Moduls mit dem Namen auf dem Datenträger übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4c904-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="4c904-111">`GetName`Gibt ein S_FALSE HRESULT zurück, wenn der Name erfunden ist, z. b. für ein dynamisches Modul oder ein in-Memory-Modul.</span><span class="sxs-lookup"><span data-stu-id="4c904-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c904-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c904-112">Requirements</span></span>  
 <span data-ttu-id="4c904-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c904-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c904-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="4c904-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c904-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c904-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c904-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c904-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c904-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c904-117">See also</span></span>
