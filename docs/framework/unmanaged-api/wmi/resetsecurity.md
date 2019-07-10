---
title: ResetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die ResetSecurity-Funktion weist ein Identitätswechseltoken für den aktuellen Thread.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3d87fa10dafba326147bcaa39836b631291ef1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783129"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="ff1ab-103">ResetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="ff1ab-103">ResetSecurity function</span></span>
<span data-ttu-id="ff1ab-104">Weist das angegebene Identitätswechseltoken dem aktuellen Thread zu.</span><span class="sxs-lookup"><span data-stu-id="ff1ab-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ff1ab-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff1ab-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="ff1ab-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff1ab-106">Parameters</span></span>

`token`  
<span data-ttu-id="ff1ab-107">[in] Token für den Identitätswechsel des aktuellen Threads zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff1ab-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="ff1ab-108">Ihr Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="ff1ab-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ff1ab-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ff1ab-109">Return value</span></span>

<span data-ttu-id="ff1ab-110">Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="ff1ab-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="ff1ab-111">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein NULL-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ff1ab-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="ff1ab-112">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="ff1ab-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ff1ab-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff1ab-113">Requirements</span></span>  
 <span data-ttu-id="ff1ab-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff1ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff1ab-115">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ff1ab-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ff1ab-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff1ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1ab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff1ab-117">See also</span></span>

- [<span data-ttu-id="ff1ab-118">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ff1ab-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
