---
title: GetQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetQualifierSet-Funktion ruft den Qualifizierer aus, legen Sie für eine Klasse oder Instanz ab.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e392d3afcd81e6eace7a674788a2a957da28842c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746471"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="0cbb9-103">GetQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="0cbb9-103">GetQualifierSet function</span></span>
<span data-ttu-id="0cbb9-104">Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0cbb9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cbb9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="0cbb9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cbb9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0cbb9-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0cbb9-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="0cbb9-109">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer des Klassenobjekts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="0cbb9-110">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="0cbb9-111">Wenn ein Fehler auftritt, wird ein neues Objekt nicht zurückgegeben wird und der Zeiger bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="0cbb9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0cbb9-112">Return value</span></span>

<span data-ttu-id="0cbb9-113">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="0cbb9-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0cbb9-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="0cbb9-114">Constant</span></span>  |<span data-ttu-id="0cbb9-115">Wert</span><span class="sxs-lookup"><span data-stu-id="0cbb9-115">Value</span></span>  |<span data-ttu-id="0cbb9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0cbb9-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0cbb9-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0cbb9-117">0x80041001</span></span> | <span data-ttu-id="0cbb9-118">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="0cbb9-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0cbb9-119">0x80041002</span></span> | <span data-ttu-id="0cbb9-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0cbb9-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0cbb9-121">0x80041006</span></span> | <span data-ttu-id="0cbb9-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0cbb9-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0cbb9-123">0x80041008</span></span> | <span data-ttu-id="0cbb9-124">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0cbb9-125">0</span><span class="sxs-lookup"><span data-stu-id="0cbb9-125">0</span></span> | <span data-ttu-id="0cbb9-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0cbb9-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cbb9-127">Remarks</span></span>

<span data-ttu-id="0cbb9-128">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) Methode.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="0cbb9-129">Die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="0cbb9-130">Eine solche hinzugefügt, bearbeitet oder gelöscht.-Qualifizierer gelten für die vollständige Definition der Instanz oder Klasse.</span><span class="sxs-lookup"><span data-stu-id="0cbb9-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="0cbb9-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cbb9-131">Requirements</span></span>  
<span data-ttu-id="0cbb9-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cbb9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cbb9-133">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0cbb9-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0cbb9-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0cbb9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbb9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cbb9-135">See also</span></span>

- [<span data-ttu-id="0cbb9-136">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0cbb9-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
