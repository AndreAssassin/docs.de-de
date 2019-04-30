---
title: ICorDebugFrame::GetFunctionToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156c16f73916d2b4efa1c1b3541a772fb43dd470
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988766"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="58ff1-102">ICorDebugFrame::GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="58ff1-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="58ff1-103">Ruft das Metadatentoken für die Funktion, die den Code für diesen Stapelrahmen enthält.</span><span class="sxs-lookup"><span data-stu-id="58ff1-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58ff1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58ff1-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58ff1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58ff1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="58ff1-106">[out] Ein Zeiger auf ein `mdMethodDef` Token, die Metadaten für die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="58ff1-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58ff1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58ff1-107">Requirements</span></span>  
 <span data-ttu-id="58ff1-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58ff1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58ff1-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58ff1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58ff1-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58ff1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58ff1-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58ff1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
