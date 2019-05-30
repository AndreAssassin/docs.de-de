---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Put schreibt benannten Qualifizierers und seinen Wert.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a11f19a9b5ebdf491b79c250da7fc5ac3d980b64
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377869"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="7d227-103">QualifierSet_Put-Funktion</span><span class="sxs-lookup"><span data-stu-id="7d227-103">QualifierSet_Put function</span></span>

<span data-ttu-id="7d227-104">Schreibt den benannten Qualifizierer und den Wert.</span><span class="sxs-lookup"><span data-stu-id="7d227-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="7d227-105">Der neue Qualifizierer wird den vorherigen Wert mit dem gleichen Namen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d227-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="7d227-106">Wenn Sie der Qualifizierer nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d227-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7d227-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d227-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="7d227-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d227-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7d227-109">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d227-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7d227-110">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="7d227-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="7d227-111">[in] Der Name des Qualifizierers schreiben.</span><span class="sxs-lookup"><span data-stu-id="7d227-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="7d227-112">[in] Ein Zeiger auf ein gültiges `VARIANT` , enthält den Qualifizierer, der zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7d227-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="7d227-113">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="7d227-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="7d227-114">[in] Einer der folgenden Konstanten, die die gewünschten Qualifizierern für diesen Qualifizierer definiert.</span><span class="sxs-lookup"><span data-stu-id="7d227-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="7d227-115">Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="7d227-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="7d227-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="7d227-116">Constant</span></span>  |<span data-ttu-id="7d227-117">Wert</span><span class="sxs-lookup"><span data-stu-id="7d227-117">Value</span></span>  |<span data-ttu-id="7d227-118">Description</span><span class="sxs-lookup"><span data-stu-id="7d227-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="7d227-119">0</span><span class="sxs-lookup"><span data-stu-id="7d227-119">0</span></span> | <span data-ttu-id="7d227-120">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7d227-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="7d227-121">**Dies ist der Standardwert.**</span><span class="sxs-lookup"><span data-stu-id="7d227-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="7d227-122">1</span><span class="sxs-lookup"><span data-stu-id="7d227-122">1</span></span> | <span data-ttu-id="7d227-123">Der Qualifizierer wird an Instanzen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="7d227-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="7d227-124">2</span><span class="sxs-lookup"><span data-stu-id="7d227-124">2</span></span> | <span data-ttu-id="7d227-125">Der Qualifizierer wird auf die abgeleitete Klassen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="7d227-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="7d227-126">0x10</span><span class="sxs-lookup"><span data-stu-id="7d227-126">0x10</span></span> | <span data-ttu-id="7d227-127">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7d227-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="7d227-128">0x80</span><span class="sxs-lookup"><span data-stu-id="7d227-128">0x80</span></span> | <span data-ttu-id="7d227-129">Der Qualifizierer wurde lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="7d227-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="7d227-130">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d227-130">Return value</span></span>

<span data-ttu-id="7d227-131">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="7d227-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7d227-132">Konstante</span><span class="sxs-lookup"><span data-stu-id="7d227-132">Constant</span></span>  |<span data-ttu-id="7d227-133">Wert</span><span class="sxs-lookup"><span data-stu-id="7d227-133">Value</span></span>  |<span data-ttu-id="7d227-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d227-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="7d227-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="7d227-135">0x8004101f</span></span> | <span data-ttu-id="7d227-136">Es wurde ein unzulässiger Versuch unternommen, an die **Schlüssel** Qualifizierer für eine Eigenschaft, die kein Schlüssel sein kann.</span><span class="sxs-lookup"><span data-stu-id="7d227-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="7d227-137">Die Schlüssel werden in der Klassendefinition für ein Objekt angegeben und können nicht individuell pro Instanz geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7d227-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7d227-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7d227-138">0x80041008</span></span> | <span data-ttu-id="7d227-139">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="7d227-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="7d227-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="7d227-140">0x80041029</span></span> | <span data-ttu-id="7d227-141">Die `pVal` Parameter ist nicht vom zulässiger Qualifizierertyp.</span><span class="sxs-lookup"><span data-stu-id="7d227-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="7d227-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="7d227-142">0x8004101a</span></span> | <span data-ttu-id="7d227-143">Es ist nicht möglich, zum Aufrufen der `QualifierSet_Put` Methode für den Qualifizierer überschreibt, da das besitzende Objekt nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="7d227-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7d227-144">0</span><span class="sxs-lookup"><span data-stu-id="7d227-144">0</span></span> | <span data-ttu-id="7d227-145">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7d227-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7d227-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d227-146">Remarks</span></span>

<span data-ttu-id="7d227-147">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) Methode.</span><span class="sxs-lookup"><span data-stu-id="7d227-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d227-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d227-148">Requirements</span></span>

<span data-ttu-id="7d227-149">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d227-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d227-150">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7d227-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7d227-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7d227-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d227-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d227-152">See also</span></span>

- [<span data-ttu-id="7d227-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="7d227-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
