---
title: CloneEnumWbemClassObject-Funktion (Referenz zur nicht verwalteten API)
description: CloneEnumWbemClassObject-Funktion ist eine logische Kopie eines Enumerators.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab660769a49cf12b129cb7f44b8378053a231f8c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761626"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="5fb91-103">CloneEnumWbemClassObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="5fb91-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="5fb91-104">Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5fb91-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5fb91-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fb91-105">Syntax</span></span>

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```

## <a name="parameters"></a><span data-ttu-id="5fb91-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fb91-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="5fb91-107">[out] Erhält einen Zeiger auf ein neues [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="5fb91-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="5fb91-108">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="5fb91-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="5fb91-109">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="5fb91-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="5fb91-110">[out] Ein Zeiger auf die [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) Instanz, geklont zu werden.</span><span class="sxs-lookup"><span data-stu-id="5fb91-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="5fb91-111">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="5fb91-111">[in] The user name.</span></span> <span data-ttu-id="5fb91-112">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="5fb91-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="5fb91-113">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="5fb91-113">[in] The password.</span></span> <span data-ttu-id="5fb91-114">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="5fb91-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="5fb91-115">`strAuthority`\ [in] der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5fb91-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="5fb91-116">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="5fb91-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="5fb91-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5fb91-117">Return value</span></span>

<span data-ttu-id="5fb91-118">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="5fb91-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5fb91-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="5fb91-119">Constant</span></span>  |<span data-ttu-id="5fb91-120">Wert</span><span class="sxs-lookup"><span data-stu-id="5fb91-120">Value</span></span>  |<span data-ttu-id="5fb91-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fb91-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="5fb91-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5fb91-122">0x80041001</span></span> | <span data-ttu-id="5fb91-123">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="5fb91-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5fb91-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5fb91-124">0x80041008</span></span> | <span data-ttu-id="5fb91-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5fb91-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5fb91-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5fb91-126">0x80041006</span></span> | <span data-ttu-id="5fb91-127">Ist nicht genügend Arbeitsspeicher verfügbar, der Vorgang abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5fb91-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="5fb91-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="5fb91-128">0x80041015</span></span> | <span data-ttu-id="5fb91-129">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="5fb91-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5fb91-130">0</span><span class="sxs-lookup"><span data-stu-id="5fb91-130">0</span></span> | <span data-ttu-id="5fb91-131">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="5fb91-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="5fb91-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fb91-132">Remarks</span></span>

<span data-ttu-id="5fb91-133">Diese Funktion umschließt einen Aufruf der [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="5fb91-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="5fb91-134">Auf diese Weise wird nur eine "best-Effort" kopieren.</span><span class="sxs-lookup"><span data-stu-id="5fb91-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="5fb91-135">Aufgrund der dynamischen Natur der viele CIM-Objekte werden soll ist es möglich, dass der neue Enumerator nicht den gleichen Satz von Objekten als Enumerator aus Quelle aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb91-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="5fb91-136">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="5fb91-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="5fb91-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fb91-137">Example</span></span>

<span data-ttu-id="5fb91-138">Ein Beispiel finden Sie unter den [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="5fb91-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5fb91-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fb91-139">Requirements</span></span>
 <span data-ttu-id="5fb91-140">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fb91-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="5fb91-141">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5fb91-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="5fb91-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb91-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5fb91-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fb91-143">See also</span></span>

- [<span data-ttu-id="5fb91-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5fb91-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
