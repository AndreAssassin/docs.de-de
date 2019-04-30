---
title: ICorDebugModule::GetGlobalVariableValu-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e747e43f67533771665313f4d420e4725945cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988090"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="59227-102">ICorDebugModule::GetGlobalVariableValu-Methode</span><span class="sxs-lookup"><span data-stu-id="59227-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="59227-103">Ruft den Wert der angegebenen globalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="59227-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59227-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59227-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59227-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="59227-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="59227-106">[in] Ein `mdFieldDef` -Token, die Metadaten zur Beschreibung der globalen Variable verweist.</span><span class="sxs-lookup"><span data-stu-id="59227-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="59227-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den Wert der angegebenen globalen Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="59227-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59227-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59227-108">Requirements</span></span>  
 <span data-ttu-id="59227-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59227-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59227-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59227-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59227-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59227-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59227-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59227-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
