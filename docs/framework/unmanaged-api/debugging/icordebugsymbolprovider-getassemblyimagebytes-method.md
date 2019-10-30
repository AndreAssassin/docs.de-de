---
title: 'Icordebugsymbolprovider:: getassemblyimagebytes-Methode'
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 3184ba116704df8945b53766e62435a4252eaa11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138939"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="e25e6-102">Icordebugsymbolprovider:: getassemblyimagebytes-Methode</span><span class="sxs-lookup"><span data-stu-id="e25e6-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="e25e6-103">Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e25e6-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e25e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e25e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e25e6-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="e25e6-106">[in] Eine relative virtuelle Adresse (RVA) in einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="e25e6-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="e25e6-107">Die Anzahl der Bytes, die aus der zusammengeführten Assembly gelesen. werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e25e6-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="e25e6-108">Ein Zeiger auf die Adresse eines [icordebugmemorybuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekts, das Informationen über den Arbeitsspeicher Puffer mit zusammengeführten Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="e25e6-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e25e6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e25e6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e25e6-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e25e6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e25e6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e25e6-111">Requirements</span></span>  
 <span data-ttu-id="e25e6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e25e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e25e6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e25e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e25e6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e25e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e25e6-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e25e6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25e6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e25e6-116">See also</span></span>

- [<span data-ttu-id="e25e6-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e25e6-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e25e6-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e25e6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
