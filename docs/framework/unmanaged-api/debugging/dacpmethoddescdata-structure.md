---
title: DacpMethodDescData-Struktur
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965905"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="25a81-102">DacpMethodDescData-Struktur</span><span class="sxs-lookup"><span data-stu-id="25a81-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="25a81-103">Definiert einen Transport-Puffer für die Runtime-Informationen von einer Methode an.</span><span class="sxs-lookup"><span data-stu-id="25a81-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="25a81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25a81-104">Syntax</span></span>

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="25a81-105">Member</span><span class="sxs-lookup"><span data-stu-id="25a81-105">Members</span></span>

| <span data-ttu-id="25a81-106">Member</span><span class="sxs-lookup"><span data-stu-id="25a81-106">Member</span></span>                       | <span data-ttu-id="25a81-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25a81-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="25a81-108">Gibt an, ob es sich bei die Laufzeit systemeigenen Code für die angegebene Instanziierungen der Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="25a81-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="25a81-109">Gibt an, wenn die Methode über vereinfachter codegenerierung dynamisch generiert wird.</span><span class="sxs-lookup"><span data-stu-id="25a81-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="25a81-110">Der Methode die Slotnummer in die Methodentabelle.</span><span class="sxs-lookup"><span data-stu-id="25a81-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="25a81-111">Erste systemeigene Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="25a81-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="25a81-112">Zeiger auf einen Puffer, die intern von der Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a81-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="25a81-113">Zeiger auf die `MethodDesc` in der Runtime.</span><span class="sxs-lookup"><span data-stu-id="25a81-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="25a81-114">Zeiger auf einen Puffer, die von der Laufzeit intern verwendet wird, um Methoden zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="25a81-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="25a81-115">Zeiger auf einen Puffer, die von der Runtime für Modulinformationen wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a81-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="25a81-116">Token, die die angegebene Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="25a81-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="25a81-117">Zeiger auf einen Garbage Collection-Puffer, die intern von der Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a81-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="25a81-118">Zeiger auf einen Garbage Collection-Puffer, die intern von der Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a81-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="25a81-119">Wenn die Methode dynamisch ist, verwendet die Runtime diesen Puffer für die Funktion zur nachverfolgung von intern.</span><span class="sxs-lookup"><span data-stu-id="25a81-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="25a81-120">Zum Auffüllen der Struktur pro Anforderung, wenn eine native Adresse verwendet.</span><span class="sxs-lookup"><span data-stu-id="25a81-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="25a81-121">Informationen über die neuesten instrumentierte Version der Methode.</span><span class="sxs-lookup"><span data-stu-id="25a81-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="25a81-122">ReJIT-Informationen für die angeforderte systemeigene Adresse.</span><span class="sxs-lookup"><span data-stu-id="25a81-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="25a81-123">Anzahl von Wiederholungen, die die Methode Rejitted durch die Instrumentierung wurde.</span><span class="sxs-lookup"><span data-stu-id="25a81-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="25a81-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25a81-124">Remarks</span></span>

<span data-ttu-id="25a81-125">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="25a81-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="25a81-126">Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a81-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="25a81-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25a81-127">Requirements</span></span>
<span data-ttu-id="25a81-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a81-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="25a81-129">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="25a81-129">**Header:** None</span></span>  
<span data-ttu-id="25a81-130">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="25a81-130">**Library:** None</span></span>  
<span data-ttu-id="25a81-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="25a81-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="25a81-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25a81-132">See also</span></span>

- [<span data-ttu-id="25a81-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="25a81-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="25a81-134">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="25a81-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="25a81-135">Allgemeine Datentypen</span><span class="sxs-lookup"><span data-stu-id="25a81-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
