---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_EndEnumeration-Funktion wird eine Enumeration beendet.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2dfd6bb521dee14afd3728bdd9c446cb779e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149226"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="22af4-103">QualifierSet_EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="22af4-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="22af4-104">Beendet die Enumeration, die mit einem Aufruf gestartet wurde die [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="22af4-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="22af4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="22af4-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="22af4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="22af4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="22af4-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="22af4-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="22af4-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="22af4-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="22af4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22af4-109">Return value</span></span>

<span data-ttu-id="22af4-110">Der folgende Wert zurückgegeben, die von dieser Funktion wird definiert, der *WbemCli.h* Header-Datei, oder Sie können ihn definieren als Konstante in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="22af4-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="22af4-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="22af4-111">Constant</span></span>  |<span data-ttu-id="22af4-112">Wert</span><span class="sxs-lookup"><span data-stu-id="22af4-112">Value</span></span>  |<span data-ttu-id="22af4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22af4-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="22af4-114">0</span><span class="sxs-lookup"><span data-stu-id="22af4-114">0</span></span> | <span data-ttu-id="22af4-115">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="22af4-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="22af4-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22af4-116">Remarks</span></span>

<span data-ttu-id="22af4-117">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="22af4-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="22af4-118">Dieser Aufruf wird empfohlen, aber nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="22af4-118">This call is recommended, but not required.</span></span> <span data-ttu-id="22af4-119">Es gibt sofort die Enumeration zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="22af4-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="22af4-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22af4-120">Requirements</span></span>  

<span data-ttu-id="22af4-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22af4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="22af4-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="22af4-122">**Header:** WMINet_Utils.idl</span></span>  
  
**<span data-ttu-id="22af4-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="22af4-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22af4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22af4-124">See also</span></span>

- [<span data-ttu-id="22af4-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="22af4-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
