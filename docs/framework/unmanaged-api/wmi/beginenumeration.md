---
title: BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: BeginEnumeration-Funktion setzt einen Enumerator zurück, auf den Anfang der enumeration
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212296"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="47d68-103">BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="47d68-103">BeginEnumeration function</span></span>
<span data-ttu-id="47d68-104">Setzt einen Enumerator zurück zum Anfang der Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="47d68-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="47d68-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47d68-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="47d68-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47d68-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="47d68-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="47d68-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="47d68-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="47d68-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="47d68-109">[in] Eine bitweise Kombination der Flags oder Werte, die in beschriebenen der ["Hinweise"](#remarks) Abschnitt, der steuert, in der Enumeration enthaltenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="47d68-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="47d68-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47d68-110">Return value</span></span>

<span data-ttu-id="47d68-111">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="47d68-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="47d68-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="47d68-112">Constant</span></span>  |<span data-ttu-id="47d68-113">Wert</span><span class="sxs-lookup"><span data-stu-id="47d68-113">Value</span></span>  |<span data-ttu-id="47d68-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47d68-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="47d68-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="47d68-115">0x80041008</span></span> | <span data-ttu-id="47d68-116">Die Kombination von Flags in `lEnumFlags` ist ungültig oder ein ungültiges Argument wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="47d68-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="47d68-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="47d68-117">0x8004101d</span></span> | <span data-ttu-id="47d68-118">Einen zweiten Aufruf von `BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="47d68-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="47d68-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="47d68-119">0x80041006</span></span> | <span data-ttu-id="47d68-120">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="47d68-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="47d68-121">0</span><span class="sxs-lookup"><span data-stu-id="47d68-121">0</span></span> | <span data-ttu-id="47d68-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="47d68-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="47d68-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47d68-123">Remarks</span></span>

<span data-ttu-id="47d68-124">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Methode.</span><span class="sxs-lookup"><span data-stu-id="47d68-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="47d68-125">Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="47d68-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="47d68-126">Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="47d68-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="47d68-127">Allerdings sind Flags aus der gleichen Gruppe sich gegenseitig ausschließende.</span><span class="sxs-lookup"><span data-stu-id="47d68-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="47d68-128">**Gruppe 1**</span><span class="sxs-lookup"><span data-stu-id="47d68-128">**Group 1**</span></span>

|<span data-ttu-id="47d68-129">Konstante</span><span class="sxs-lookup"><span data-stu-id="47d68-129">Constant</span></span>  |<span data-ttu-id="47d68-130">Wert</span><span class="sxs-lookup"><span data-stu-id="47d68-130">Value</span></span>  |<span data-ttu-id="47d68-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47d68-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="47d68-132">0x4</span><span class="sxs-lookup"><span data-stu-id="47d68-132">0x4</span></span> | <span data-ttu-id="47d68-133">Enthalten Sie die Eigenschaften, die nur den Schlüssel zu bilden.</span><span class="sxs-lookup"><span data-stu-id="47d68-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="47d68-134">0x8</span><span class="sxs-lookup"><span data-stu-id="47d68-134">0x8</span></span> | <span data-ttu-id="47d68-135">Enthalten Sie die Eigenschaften, die nur die Objektverweise sind.</span><span class="sxs-lookup"><span data-stu-id="47d68-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="47d68-136">**Gruppe 2**</span><span class="sxs-lookup"><span data-stu-id="47d68-136">**Group 2**</span></span>

<span data-ttu-id="47d68-137">Konstante</span><span class="sxs-lookup"><span data-stu-id="47d68-137">Constant</span></span>  |<span data-ttu-id="47d68-138">Wert</span><span class="sxs-lookup"><span data-stu-id="47d68-138">Value</span></span>  |<span data-ttu-id="47d68-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47d68-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="47d68-140">0x30</span><span class="sxs-lookup"><span data-stu-id="47d68-140">0x30</span></span> | <span data-ttu-id="47d68-141">Die Enumeration, die nur die Systemeigenschaften zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="47d68-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="47d68-142">0x40</span><span class="sxs-lookup"><span data-stu-id="47d68-142">0x40</span></span> | <span data-ttu-id="47d68-143">Lokale und verteilte Eigenschaften enthalten, aber Ausschließen von Eigenschaften aus der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="47d68-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="47d68-144">Für Klassen:</span><span class="sxs-lookup"><span data-stu-id="47d68-144">For classes:</span></span>

<span data-ttu-id="47d68-145">Konstante</span><span class="sxs-lookup"><span data-stu-id="47d68-145">Constant</span></span>  |<span data-ttu-id="47d68-146">Wert</span><span class="sxs-lookup"><span data-stu-id="47d68-146">Value</span></span>  |<span data-ttu-id="47d68-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47d68-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="47d68-148">0x100</span><span class="sxs-lookup"><span data-stu-id="47d68-148">0x100</span></span> | <span data-ttu-id="47d68-149">Beschränken Sie die Enumeration, die Eigenschaften, die in der Definition der Klasse überschrieben.</span><span class="sxs-lookup"><span data-stu-id="47d68-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="47d68-150">0x100</span><span class="sxs-lookup"><span data-stu-id="47d68-150">0x100</span></span> | <span data-ttu-id="47d68-151">Beschränken Sie die Enumeration, die den Eigenschaften, die in der Definition der aktuellen Klasse überschrieben und den neuen Eigenschaften, die in der Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="47d68-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="47d68-152">0x300</span><span class="sxs-lookup"><span data-stu-id="47d68-152">0x300</span></span> | <span data-ttu-id="47d68-153">Ein zu maskieren (anstatt ein Flag) vor dem Anwenden einer `lEnumFlags` Wert entweder überprüft, ob `WBEM_FLAG_CLASS_OVERRIDES_ONLY` oder `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="47d68-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="47d68-154">0x10</span><span class="sxs-lookup"><span data-stu-id="47d68-154">0x10</span></span> | <span data-ttu-id="47d68-155">Beschränken Sie die Enumeration auf Eigenschaften, die definiert, oder in der Klasse selbst geändert werden.</span><span class="sxs-lookup"><span data-stu-id="47d68-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="47d68-156">0x20</span><span class="sxs-lookup"><span data-stu-id="47d68-156">0x20</span></span> | <span data-ttu-id="47d68-157">Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="47d68-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="47d68-158">Für Instanzen:</span><span class="sxs-lookup"><span data-stu-id="47d68-158">For instances:</span></span>

<span data-ttu-id="47d68-159">Konstante</span><span class="sxs-lookup"><span data-stu-id="47d68-159">Constant</span></span>  |<span data-ttu-id="47d68-160">Wert</span><span class="sxs-lookup"><span data-stu-id="47d68-160">Value</span></span>  |<span data-ttu-id="47d68-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47d68-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="47d68-162">0x10</span><span class="sxs-lookup"><span data-stu-id="47d68-162">0x10</span></span> | <span data-ttu-id="47d68-163">Beschränken Sie die Enumeration auf Eigenschaften, die definiert, oder in der Klasse selbst geändert werden.</span><span class="sxs-lookup"><span data-stu-id="47d68-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="47d68-164">0x20</span><span class="sxs-lookup"><span data-stu-id="47d68-164">0x20</span></span> | <span data-ttu-id="47d68-165">Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="47d68-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="47d68-166">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47d68-166">Requirements</span></span>  
 <span data-ttu-id="47d68-167">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47d68-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d68-168">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="47d68-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="47d68-169">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47d68-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d68-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47d68-170">See also</span></span>

- [<span data-ttu-id="47d68-171">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="47d68-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)