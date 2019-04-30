---
title: ICorProfilerInfo::GetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2960bc0cfc39adb9b7cbca236d495baf630a173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991847"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="ecc0d-102">ICorProfilerInfo::GetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="ecc0d-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="ecc0d-103">Ruft einen Zeiger auf den Text einer Methode in Microsoft intermediate Language (MSIL)-Code, beginnend mit dem Header an.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecc0d-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecc0d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ecc0d-106">[in] Die ID des Moduls, in dem die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="ecc0d-107">[in] Das Metadatentoken für die Methode.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="ecc0d-108">[out] Ein Zeiger auf den Header der Methode.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="ecc0d-109">[out] Eine ganze Zahl, die die Größe der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc0d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecc0d-110">Remarks</span></span>  
 <span data-ttu-id="ecc0d-111">Eine Methode ist das Modul beschränkt, in dem er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="ecc0d-112">Da die `GetILFunctionBody` -Methode entwickelt, um den MSIL-Code eine Toolzugriff gewähren, bevor es von der common Language Runtime (CLR) geladen wurde, es verwendet das Metadatentoken der Methode aus, um die gewünschte Instanz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="ecc0d-113">`GetILFunctionBody` kann ein CORPROF_E_FUNCTION_NOT_IL HRESULT zurückgeben, wenn die `methodId` verweist auf eine Methode ohne MSIL-code (z. B. PInvoke-Methode aufrufen, eine abstrakte Methode oder eine Plattform).</span><span class="sxs-lookup"><span data-stu-id="ecc0d-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc0d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecc0d-114">Requirements</span></span>  
 <span data-ttu-id="ecc0d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc0d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc0d-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecc0d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecc0d-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc0d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc0d-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc0d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc0d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecc0d-119">See also</span></span>

- [<span data-ttu-id="ecc0d-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecc0d-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
