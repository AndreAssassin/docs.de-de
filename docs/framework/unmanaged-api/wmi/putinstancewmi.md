---
title: PutInstanceWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion PutInstanceWmi erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19f657fd76f73c4016824511079e6f037bc3bc53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597327"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="36bc7-103">PutInstanceWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="36bc7-103">PutInstanceWmi function</span></span>

<span data-ttu-id="36bc7-104">Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="36bc7-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="36bc7-105">Die Instanz wird in das WMI-Repository geschrieben.</span><span class="sxs-lookup"><span data-stu-id="36bc7-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="36bc7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="36bc7-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="36bc7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="36bc7-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="36bc7-108">[in] Ein Zeiger auf die Instanz geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="36bc7-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="36bc7-109">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="36bc7-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="36bc7-110">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="36bc7-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36bc7-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="36bc7-111">Constant</span></span>  |<span data-ttu-id="36bc7-112">Wert</span><span class="sxs-lookup"><span data-stu-id="36bc7-112">Value</span></span>  |<span data-ttu-id="36bc7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36bc7-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="36bc7-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="36bc7-114">0x20000</span></span> | <span data-ttu-id="36bc7-115">Wenn festgelegt, WMI keine keine Qualifizierer mit speichert die **Amended** Flavor.</span><span class="sxs-lookup"><span data-stu-id="36bc7-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="36bc7-116">Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt ist nicht lokalisiert werden soll, und alle Qualifizierer werden mit dieser Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="36bc7-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="36bc7-117">0</span><span class="sxs-lookup"><span data-stu-id="36bc7-117">0</span></span> | <span data-ttu-id="36bc7-118">Erstellen Sie die Instanz aus, wenn er nicht vorhanden ist, oder überschrieben, falls sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="36bc7-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="36bc7-119">1</span><span class="sxs-lookup"><span data-stu-id="36bc7-119">1</span></span> | <span data-ttu-id="36bc7-120">Aktualisieren Sie die Instanz.</span><span class="sxs-lookup"><span data-stu-id="36bc7-120">Update the instance.</span></span> <span data-ttu-id="36bc7-121">Die Instanz muss vorhanden sein, der Aufruf erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="36bc7-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="36bc7-122">2</span><span class="sxs-lookup"><span data-stu-id="36bc7-122">2</span></span> | <span data-ttu-id="36bc7-123">Erstellen Sie die Instanz.</span><span class="sxs-lookup"><span data-stu-id="36bc7-123">Create the instance.</span></span> <span data-ttu-id="36bc7-124">Der Aufruf schlägt fehl, wenn die Instanz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="36bc7-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="36bc7-125">0x10</span><span class="sxs-lookup"><span data-stu-id="36bc7-125">0x10</span></span> | <span data-ttu-id="36bc7-126">Das Flag wird halbsynchron aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="36bc7-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="36bc7-127">[in] Dieser Wert in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="36bc7-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="36bc7-128">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="36bc7-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="36bc7-129">[out] Wenn `null`, dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="36bc7-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="36bc7-130">Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort zurück `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="36bc7-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="36bc7-131">Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) Objekt.</span><span class="sxs-lookup"><span data-stu-id="36bc7-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="36bc7-132">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36bc7-132">Return value</span></span>

<span data-ttu-id="36bc7-133">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="36bc7-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36bc7-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="36bc7-134">Constant</span></span>  |<span data-ttu-id="36bc7-135">Wert</span><span class="sxs-lookup"><span data-stu-id="36bc7-135">Value</span></span>  |<span data-ttu-id="36bc7-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36bc7-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="36bc7-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="36bc7-137">0x80041003</span></span> | <span data-ttu-id="36bc7-138">Der Benutzer nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="36bc7-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="36bc7-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="36bc7-139">0x80041001</span></span> | <span data-ttu-id="36bc7-140">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="36bc7-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="36bc7-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="36bc7-141">0x80041010</span></span> | <span data-ttu-id="36bc7-142">Die Klasse, die Unterstützung von dieser Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="36bc7-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="36bc7-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="36bc7-143">0x80041028</span></span> | <span data-ttu-id="36bc7-144">eine `null` wurde für eine Eigenschaft, die kann nicht angegeben `null`, z. B. ein, die gekennzeichnet ist, indem ein **indiziert** oder **Not_Null** Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="36bc7-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="36bc7-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="36bc7-145">0x8004100f</span></span> | <span data-ttu-id="36bc7-146">Die angegebene Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="36bc7-146">The specified instance is not valid.</span></span> <span data-ttu-id="36bc7-147">(Zum Beispiel der Aufruf `PutInstanceWmi` mit einer Klasse gibt diesen Wert zurück.)</span><span class="sxs-lookup"><span data-stu-id="36bc7-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="36bc7-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="36bc7-148">0x80041008</span></span> | <span data-ttu-id="36bc7-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="36bc7-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="36bc7-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="36bc7-150">0x80041019</span></span> | <span data-ttu-id="36bc7-151">Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Instanz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="36bc7-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="36bc7-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="36bc7-152">0x80041002</span></span> | <span data-ttu-id="36bc7-153">`WBEM_FLAG_UPDATE_ONLY` in wurde angegeben `lFlags`, aber die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="36bc7-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="36bc7-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="36bc7-154">0x80041006</span></span> | <span data-ttu-id="36bc7-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="36bc7-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="36bc7-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="36bc7-156">0x80041033</span></span> | <span data-ttu-id="36bc7-157">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="36bc7-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="36bc7-158">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="36bc7-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="36bc7-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="36bc7-159">0x80041015</span></span> | <span data-ttu-id="36bc7-160">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="36bc7-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="36bc7-161">0</span><span class="sxs-lookup"><span data-stu-id="36bc7-161">0</span></span> | <span data-ttu-id="36bc7-162">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="36bc7-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="36bc7-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36bc7-163">Remarks</span></span>

<span data-ttu-id="36bc7-164">Diese Funktion umschließt einen Aufruf der [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) Methode.</span><span class="sxs-lookup"><span data-stu-id="36bc7-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="36bc7-165">Die `PutInstanceWmi` unterstützt das Erstellen von Instanzen und Aktualisierung von vorhandenen Klassen nur Instanzen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="36bc7-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="36bc7-166">Je nachdem, wie der `pCtx` Parameter festgelegt ist, einige oder alle Eigenschaften der Instanz aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="36bc7-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="36bc7-167">Wenn die Instanz verweist `pInst` gehört zu einer Unterklasse, die Windows-Verwaltung Ruft alle Anbieter, die verantwortlich für die Klassen, die von der die Unterklasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="36bc7-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="36bc7-168">Alle diese Anbieter muss erfolgreich sein, für die ursprüngliche `PutInstanceWmi` -Anforderung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="36bc7-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="36bc7-169">Der Anbieter oberste Klasse in der Hierarchie unterstützt, wird zuerst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="36bc7-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="36bc7-170">Die Aufrufreihenfolge weiterhin mit der Unterklasse der obersten-Klasse und von oben nach unten verläuft wird, bis Windows-Verwaltung den Anbieter für die Klasse, die Besitzer der Instanz verweist erreicht `pInst`.</span><span class="sxs-lookup"><span data-stu-id="36bc7-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="36bc7-171">Windows-Verwaltung wird die Anbieter für alle untergeordneten Klassen einer Instanz nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="36bc7-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="36bc7-172">Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie, gehört die `pInst` Parameter muss mit der Instanz, die mit den zu ändernden Eigenschaften verweisen.</span><span class="sxs-lookup"><span data-stu-id="36bc7-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="36bc7-173">Beachten Sie, also eine Zielinstanz, die angehört **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="36bc7-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="36bc7-174">Die **ClassB** Instanz leitet sich von **ClassA**, und **ClassA** definiert die Eigenschaft **PropA**.</span><span class="sxs-lookup"><span data-stu-id="36bc7-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="36bc7-175">Wenn eine Anwendung eine Änderung an den Wert der vornehmen möchte **PropA** in die **ClassB** -Instanz müssen sie festlegen `pInst` auf diese Instanz und nicht auf einer Instanz von **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="36bc7-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="36bc7-176">Aufrufen von `PutInstanceWmi` auf einer Instanz einer abstrakten Klasse ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="36bc7-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="36bc7-177">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="36bc7-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="36bc7-178">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36bc7-178">Requirements</span></span>

<span data-ttu-id="36bc7-179">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36bc7-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="36bc7-180">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="36bc7-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="36bc7-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36bc7-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="36bc7-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36bc7-182">See also</span></span>

- [<span data-ttu-id="36bc7-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="36bc7-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)