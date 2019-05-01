---
title: CompareTo-Funktionen (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt in einen anderen WMI-Objekt.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb5a26fccf7ceb56089aae4bd4f0732b8a405ba0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049270"
---
# <a name="compareto-function"></a><span data-ttu-id="9c841-103">CompareTo-Funktion</span><span class="sxs-lookup"><span data-stu-id="9c841-103">CompareTo function</span></span>

<span data-ttu-id="9c841-104">Vergleicht ein Objekt mit einem anderen Windows-Verwaltungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="9c841-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9c841-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c841-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="9c841-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c841-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="9c841-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c841-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="9c841-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="9c841-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="9c841-109">[in] Eine bitweise Kombination der Flags, die angeben, die Merkmale für den Vergleich zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9c841-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="9c841-110">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="9c841-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="9c841-111">[in] Das Objekt für den Vergleich.</span><span class="sxs-lookup"><span data-stu-id="9c841-111">[in] The object for comparison.</span></span> <span data-ttu-id="9c841-112">`pCompareTo` muss ein gültiger [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz ist nicht möglich `null`.</span><span class="sxs-lookup"><span data-stu-id="9c841-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9c841-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9c841-113">Return value</span></span>

<span data-ttu-id="9c841-114">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="9c841-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9c841-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="9c841-115">Constant</span></span>  |<span data-ttu-id="9c841-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9c841-116">Value</span></span>  |<span data-ttu-id="9c841-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c841-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="9c841-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="9c841-118">0x80041001</span></span> | <span data-ttu-id="9c841-119">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9c841-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9c841-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9c841-120">0x80041008</span></span> | <span data-ttu-id="9c841-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="9c841-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="9c841-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="9c841-122">0x8004101d</span></span> | <span data-ttu-id="9c841-123">Einen zweiten Aufruf von `BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9c841-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9c841-124">0</span><span class="sxs-lookup"><span data-stu-id="9c841-124">0</span></span> | <span data-ttu-id="9c841-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9c841-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="9c841-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="9c841-126">0x40003</span></span> | <span data-ttu-id="9c841-127">Die Objekte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9c841-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="9c841-128">0</span><span class="sxs-lookup"><span data-stu-id="9c841-128">0</span></span> | <span data-ttu-id="9c841-129">Die Objekte sind gleich basierend auf die Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="9c841-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9c841-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c841-130">Remarks</span></span>

<span data-ttu-id="9c841-131">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) Methode.</span><span class="sxs-lookup"><span data-stu-id="9c841-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="9c841-132">Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="9c841-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="9c841-133">Sie können die einzelnen Eigenschaften, die im Vergleich zum angeben, indem eine bitweise Kombination der folgenden Flags angeben:</span><span class="sxs-lookup"><span data-stu-id="9c841-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="9c841-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="9c841-134">Constant</span></span>  |<span data-ttu-id="9c841-135">Wert</span><span class="sxs-lookup"><span data-stu-id="9c841-135">Value</span></span>  |<span data-ttu-id="9c841-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c841-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="9c841-137">2</span><span class="sxs-lookup"><span data-stu-id="9c841-137">2</span></span> | <span data-ttu-id="9c841-138">Ignorieren Sie die Quelle (die Server und der Namespace, die von dem sie stammen).</span><span class="sxs-lookup"><span data-stu-id="9c841-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="9c841-139">1</span><span class="sxs-lookup"><span data-stu-id="9c841-139">1</span></span> | <span data-ttu-id="9c841-140">Ignorieren Sie alle Qualifizierer (einschließlich **Schlüssel** und **dynamische**)</span><span class="sxs-lookup"><span data-stu-id="9c841-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="9c841-141">4</span><span class="sxs-lookup"><span data-stu-id="9c841-141">4</span></span> | <span data-ttu-id="9c841-142">Ignorieren Sie die Standardwerte von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9c841-142">Ignore default values of properties.</span></span> <span data-ttu-id="9c841-143">Dieses Flag gilt nur für Vergleich von Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c841-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="9c841-144">0x20</span><span class="sxs-lookup"><span data-stu-id="9c841-144">0x20</span></span> | <span data-ttu-id="9c841-145">Varianten von Qualifizierern ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="9c841-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="9c841-146">Dieses Flag immer noch berücksichtigt Qualifizierer, aber ignoriert Flavor Unterschiede, z. B. weitergaberegeln und Einschränkungen beim Überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9c841-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="9c841-147">0x10</span><span class="sxs-lookup"><span data-stu-id="9c841-147">0x10</span></span> | <span data-ttu-id="9c841-148">Ignorieren von Groß-/Kleinschreibung im Vergleichen von Zeichenfolgenwerten.</span><span class="sxs-lookup"><span data-stu-id="9c841-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="9c841-149">Dies gilt sowohl für Zeichenfolgen und Qualifiziererwerte.</span><span class="sxs-lookup"><span data-stu-id="9c841-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="9c841-150">Beim Vergleich von Eigenschaften-und Qualifizierernamen wird immer Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9c841-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="9c841-151">0x8</span><span class="sxs-lookup"><span data-stu-id="9c841-151">0x8</span></span> | <span data-ttu-id="9c841-152">Wird davon ausgegangen Sie, dass die verglichenen Objekte Instanzen derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="9c841-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="9c841-153">Daher wird dieses Flag nur instanzbezogenen Informationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="9c841-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="9c841-154">Verwenden Sie diese Flags zum Optimieren der Leistung.</span><span class="sxs-lookup"><span data-stu-id="9c841-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="9c841-155">Wenn die Objekte nicht von derselben Klasse vorhanden sind, sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="9c841-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="9c841-156">Oder Sie können einem einzigen zusammengesetzten Flag wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="9c841-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="9c841-157">Konstante</span><span class="sxs-lookup"><span data-stu-id="9c841-157">Constant</span></span>  |<span data-ttu-id="9c841-158">Wert</span><span class="sxs-lookup"><span data-stu-id="9c841-158">Value</span></span>  |<span data-ttu-id="9c841-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c841-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="9c841-160">0</span><span class="sxs-lookup"><span data-stu-id="9c841-160">0</span></span> | <span data-ttu-id="9c841-161">Berücksichtigen Sie alle Features im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="9c841-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="9c841-162">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c841-162">Requirements</span></span>

<span data-ttu-id="9c841-163">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c841-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9c841-164">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9c841-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="9c841-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c841-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9c841-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c841-166">See also</span></span>

- [<span data-ttu-id="9c841-167">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9c841-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)