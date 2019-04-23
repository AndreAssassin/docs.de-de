---
title: ICorProfilerInfo::GetILToNativeMapping-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7bbf0e03fc69332f77f3ac34a399a96f638da3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206719"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="0b48b-102">ICorProfilerInfo::GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="0b48b-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="0b48b-103">Ruft für den in der angegebenen Funktion enthaltenen Code eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu systemeigenen Offsets ab.</span><span class="sxs-lookup"><span data-stu-id="0b48b-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b48b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b48b-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b48b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b48b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0b48b-106">[in] Die ID der Funktion, die den Code enthält.</span><span class="sxs-lookup"><span data-stu-id="0b48b-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="0b48b-107">[in] Die maximale Größe des `map`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0b48b-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="0b48b-108">[out] Die Gesamtanzahl verfügbarer COR_DEBUG_IL_TO_NATIVE_MAP-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="0b48b-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="0b48b-109">[out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, die jeweils die Offsets angeben.</span><span class="sxs-lookup"><span data-stu-id="0b48b-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="0b48b-110">Nach Rückgabe der `GetILToNativeMapping`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.</span><span class="sxs-lookup"><span data-stu-id="0b48b-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b48b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b48b-111">Remarks</span></span>  
 <span data-ttu-id="0b48b-112">Die `GetILToNativeMapping`-Methode gibt ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zurück.</span><span class="sxs-lookup"><span data-stu-id="0b48b-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="0b48b-113">Um zu beschreiben, dass bestimmte Bereiche systemeigener Anweisungen besonderen Codebereichen (beispielsweise dem Prolog) entsprechen, haben ein Eintrag im Array dessen `ilOffset` Feld festgelegt werden, auf den Wert der [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b48b-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0b48b-114">Nachdem `GetILToNativeMapping` ausgeführt ist, müssen Sie sich vergewissern, dass der `map`-Puffer groß genug war, um alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b48b-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="0b48b-115">Vergleichen Sie hierzu den Wert von `cMap` mit dem Wert des `pcMap`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="0b48b-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="0b48b-116">Wenn der `pcMap`-Wert nach Multiplikation mit der Größe einer `COR_DEBUG_IL_TO_NATIVE_MAP`-Struktur größer als `cMap` ist, weisen Sie einen größeren `map`-Puffer zu, aktualisieren Sie `cMap` mit der neuen Größe, und rufen Sie `GetILToNativeMapping` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="0b48b-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="0b48b-117">Alternativ können Sie zuerst `GetILToNativeMapping` mit einem `map`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0b48b-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="0b48b-118">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcMap` zurückgegeben wurde, und `GetILToNativeMapping` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0b48b-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b48b-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b48b-119">Requirements</span></span>  
 <span data-ttu-id="0b48b-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b48b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b48b-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b48b-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b48b-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b48b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b48b-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b48b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b48b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b48b-124">See also</span></span>

- [<span data-ttu-id="0b48b-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b48b-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0b48b-126">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="0b48b-126">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="0b48b-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0b48b-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0b48b-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="0b48b-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
