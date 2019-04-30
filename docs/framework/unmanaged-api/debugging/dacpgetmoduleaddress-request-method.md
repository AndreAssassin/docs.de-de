---
title: DacpGetModuleAddress::Request-Methode
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965899"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="6c54c-102">DacpGetModuleAddress::Request-Methode</span><span class="sxs-lookup"><span data-stu-id="6c54c-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="6c54c-103">Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6c54c-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6c54c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c54c-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="6c54c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c54c-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="6c54c-106">[in] Ein Zeiger auf die Seed-Data-Modul.</span><span class="sxs-lookup"><span data-stu-id="6c54c-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c54c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c54c-107">Remarks</span></span>

<span data-ttu-id="6c54c-108">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6c54c-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6c54c-109">Um es zu verwenden, ist die einfachste Möglichkeit, um die Implementierung zu imitieren:</span><span class="sxs-lookup"><span data-stu-id="6c54c-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="6c54c-110">Rückgabewert von Aufrufen der `Request` Methode für die `IXCLRDataModule*` Parameter mit den folgenden Parametern: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="6c54c-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="6c54c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c54c-111">Requirements</span></span>

<span data-ttu-id="6c54c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c54c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6c54c-113">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="6c54c-113">**Header:** None</span></span>     
<span data-ttu-id="6c54c-114">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="6c54c-114">**Library:** None</span></span>  
<span data-ttu-id="6c54c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c54c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c54c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c54c-116">See also</span></span>

- [<span data-ttu-id="6c54c-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6c54c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6c54c-118">DacpGetModuleAddress-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c54c-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)