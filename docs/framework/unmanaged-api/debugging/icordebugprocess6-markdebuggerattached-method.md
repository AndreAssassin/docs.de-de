---
title: ICorDebugProcess6::MarkDebuggerAttached-Methode
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15e2e94ac4e30fbdb375175148a5b448c51821f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948602"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="35cfa-102">ICorDebugProcess6::MarkDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="35cfa-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="35cfa-103">Ändert den internen Status des zu debuggenden Objekts, sodass die <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode in der .NET Framework-Klassenbibliothek `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="35cfa-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35cfa-104">Syntax</span></span>  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35cfa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35cfa-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="35cfa-106">`true`, falls sich bei der <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode herausstellt, dass ein Debugger verbunden ist; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="35cfa-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35cfa-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35cfa-107">Return Value</span></span>  
 <span data-ttu-id="35cfa-108">Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="35cfa-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="35cfa-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35cfa-109">Return value</span></span>|<span data-ttu-id="35cfa-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35cfa-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="35cfa-111">Die zu debuggende Komponente wurde erfolgreich aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="35cfa-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="35cfa-112">Die Assembly mit der <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode wurde nicht geladen, oder ein anderer Fehler wie fehlende Metadaten verhindert deren Erkennung.</span><span class="sxs-lookup"><span data-stu-id="35cfa-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="35cfa-113">Dieser Fehler ist nicht außergewöhnlich und unkritisch.</span><span class="sxs-lookup"><span data-stu-id="35cfa-113">This error is common and benign.</span></span> <span data-ttu-id="35cfa-114">Sie sollten die Methode erneut aufrufen, wenn zusätzliche Assemblys geladen werden.</span><span class="sxs-lookup"><span data-stu-id="35cfa-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="35cfa-115">Andere fehlerhafte `HRESULT`-Werte.</span><span class="sxs-lookup"><span data-stu-id="35cfa-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="35cfa-116">Andere Werte deuten wahrscheinlich auf fehlerhafte Vorgänge von Debugger- oder Compilerkomponenten hin.</span><span class="sxs-lookup"><span data-stu-id="35cfa-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35cfa-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35cfa-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35cfa-118">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35cfa-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35cfa-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35cfa-119">Requirements</span></span>  
 <span data-ttu-id="35cfa-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35cfa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35cfa-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35cfa-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35cfa-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35cfa-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35cfa-123">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35cfa-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cfa-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35cfa-124">See also</span></span>

- [<span data-ttu-id="35cfa-125">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35cfa-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="35cfa-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="35cfa-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
