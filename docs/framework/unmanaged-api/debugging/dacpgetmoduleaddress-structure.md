---
title: DacpGetModuleAddress-Struktur
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 145b06f89b45b165b9d6329a4c16ac5739406113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739181"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="ad110-102">DacpGetModuleAddress-Struktur</span><span class="sxs-lookup"><span data-stu-id="ad110-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="ad110-103">Definiert den Container für eine Anforderung zum modulimport Adresse an.</span><span class="sxs-lookup"><span data-stu-id="ad110-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ad110-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad110-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="ad110-105">Member</span><span class="sxs-lookup"><span data-stu-id="ad110-105">Members</span></span>

| <span data-ttu-id="ad110-106">Member</span><span class="sxs-lookup"><span data-stu-id="ad110-106">Member</span></span>      | <span data-ttu-id="ad110-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad110-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="ad110-108">Der Zeiger auf das Modul.</span><span class="sxs-lookup"><span data-stu-id="ad110-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="ad110-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="ad110-109">Methods</span></span>

| <span data-ttu-id="ad110-110">Methode</span><span class="sxs-lookup"><span data-stu-id="ad110-110">Method</span></span>                                                                                               | <span data-ttu-id="ad110-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad110-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="ad110-112">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ad110-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="ad110-113">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="ad110-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ad110-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad110-114">Remarks</span></span>

<span data-ttu-id="ad110-115">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ad110-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ad110-116">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="ad110-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad110-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad110-117">Requirements</span></span>
<span data-ttu-id="ad110-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad110-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ad110-119">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="ad110-119">**Header:** None</span></span>  
<span data-ttu-id="ad110-120">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="ad110-120">**Library:** None</span></span>  
<span data-ttu-id="ad110-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ad110-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad110-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad110-122">See also</span></span>

- [<span data-ttu-id="ad110-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ad110-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ad110-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ad110-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
