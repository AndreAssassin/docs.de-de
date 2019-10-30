---
title: ICorDebugFunction-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: eb2b1e218314be01898ce90c4378fb713f9bf6ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137850"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="d5c14-102">ICorDebugFunction-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5c14-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="d5c14-103">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="d5c14-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5c14-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d5c14-104">Methods</span></span>  
  
|<span data-ttu-id="d5c14-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-105">Method</span></span>|<span data-ttu-id="d5c14-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5c14-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5c14-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="d5c14-108">Erstellt am Anfang dieser Funktion einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="d5c14-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="d5c14-109">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="d5c14-110">Ruft ein ICorDebugClass-Objekt ab, das die Klasse darstellt, deren Member diese Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="d5c14-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="d5c14-111">GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="d5c14-112">Ruft die Versionsnummer der aktuellen Bearbeitung ab, die an dieser Funktion vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="d5c14-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="d5c14-113">GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="d5c14-114">Ruft den MSIL-Code (Microsoft Intermediate Language) für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="d5c14-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="d5c14-115">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="d5c14-116">Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion ab, die von dieser `ICorDebugFunction` Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d5c14-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="d5c14-117">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="d5c14-118">Ruft das Modul ab, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d5c14-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="d5c14-119">GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="d5c14-120">Ruft den nativen Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="d5c14-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="d5c14-121">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d5c14-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="d5c14-122">Ruft das Metadatentoken für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="d5c14-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5c14-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5c14-123">Remarks</span></span>  
 <span data-ttu-id="d5c14-124">Die `ICorDebugFunction`-Schnittstelle stellt keine Funktion mit generischen Typparametern dar.</span><span class="sxs-lookup"><span data-stu-id="d5c14-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="d5c14-125">Beispielsweise würde eine `ICorDebugFunction` Instanz `Func<T>`, aber nicht `Func<string>`darstellen.</span><span class="sxs-lookup"><span data-stu-id="d5c14-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="d5c14-126">Ruft [ICorDebugILFrame2:: enumeratetypeer Parameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) auf, um die generischen Typparameter abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d5c14-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="d5c14-127">Die Beziehung zwischen dem Metadatentoken einer Methode, `mdMethodDef`und dem `ICorDebugFunction` Objekt einer Methode hängt davon ab, ob "Bearbeiten und Fortfahren" für die Funktion zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="d5c14-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="d5c14-128">Wenn für die Funktion "Bearbeiten und Fortfahren" nicht zulässig ist, besteht eine 1:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d5c14-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="d5c14-129">Das heißt, die Funktion verfügt über ein `ICorDebugFunction` Objekt und ein `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d5c14-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="d5c14-130">Wenn für die Funktion "Bearbeiten und Fortfahren" zulässig ist, besteht eine n:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d5c14-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="d5c14-131">Das heißt, die Funktion kann über viele Instanzen von `ICorDebugFunction`verfügen, eine für jede Version der Funktion, aber nur ein `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="d5c14-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5c14-132">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5c14-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5c14-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5c14-133">Requirements</span></span>  
 <span data-ttu-id="d5c14-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5c14-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c14-135">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5c14-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5c14-136">**Bibliothek:**  Corguids. lib</span><span class="sxs-lookup"><span data-stu-id="d5c14-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5c14-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c14-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c14-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5c14-138">See also</span></span>

- [<span data-ttu-id="d5c14-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5c14-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
