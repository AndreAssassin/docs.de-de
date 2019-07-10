---
title: IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d7c395e68ad5d8042f9850f25757a5aa445e5c40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752686"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="dde36-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span><span class="sxs-lookup"><span data-stu-id="dde36-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="dde36-103">Stellt ein Handle zum Auflisten von der Methodeninstanzen von `AppDomain` ab einer angegebenen Adresse.</span><span class="sxs-lookup"><span data-stu-id="dde36-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dde36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dde36-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="dde36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dde36-105">Parameters</span></span>

`address`\
<span data-ttu-id="dde36-106">[in] Die Adresse der ersten Methodeninstanz.</span><span class="sxs-lookup"><span data-stu-id="dde36-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="dde36-107">[in] Die AppDomain der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="dde36-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="dde36-108">[out] Ein Handle für das Auflisten der Methodeninstanzen.</span><span class="sxs-lookup"><span data-stu-id="dde36-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="dde36-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dde36-109">Remarks</span></span>

<span data-ttu-id="dde36-110">Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 27. Steckplatz der virtuellen Methodentabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="dde36-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="dde36-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dde36-111">Requirements</span></span>

<span data-ttu-id="dde36-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dde36-113">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="dde36-113">**Header:** None</span></span>  
<span data-ttu-id="dde36-114">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="dde36-114">**Library:** None</span></span>  
<span data-ttu-id="dde36-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dde36-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="dde36-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dde36-116">See also</span></span>

- [<span data-ttu-id="dde36-117">CLRDataSourceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dde36-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="dde36-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="dde36-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="dde36-119">IXCLRDataProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dde36-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
