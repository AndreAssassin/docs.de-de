---
title: ICorDebugAppDomain2::GetArrayOrPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd8f71ca75a795ab86c61140eacbbcfb0a18b590
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737807"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="deec1-102">ICorDebugAppDomain2::GetArrayOrPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="deec1-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="deec1-103">Ruft ein Array von den angegebenen Typ oder ein Zeiger oder Verweis auf den angegebenen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="deec1-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deec1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="deec1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deec1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="deec1-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="deec1-106">[in] Ein Wert, der CorElementType-Enumeration, die angibt, den zugrunde liegenden systemeigenen Typ (ein Array, Zeiger oder Verweis) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="deec1-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="deec1-107">[in] Der Rang (d. h. die Anzahl der Dimensionen) des Arrays.</span><span class="sxs-lookup"><span data-stu-id="deec1-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="deec1-108">Dieser Wert muss 0 sein, wenn `elementType` gibt einen Zeiger oder Verweis-Typ.</span><span class="sxs-lookup"><span data-stu-id="deec1-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="deec1-109">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des Arrays darstellt, Zeiger oder Verweis erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="deec1-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="deec1-110">[out] Ein Zeiger auf die Adresse einer `ICorDebugType` geben-Objekt, das erstellte Array, Zeigertyp oder Verweis darstellt.</span><span class="sxs-lookup"><span data-stu-id="deec1-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deec1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="deec1-111">Remarks</span></span>  
 <span data-ttu-id="deec1-112">Der Wert des *ElementType* muss eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="deec1-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="deec1-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="deec1-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="deec1-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="deec1-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="deec1-115">ELEMENT_TYPE_ARRAY oder ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="deec1-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="deec1-116">Wenn der Wert des *ElementType* ELEMENT_TYPE_PTR oder ELEMENT_TYPE_BYREF, *nRank* muss NULL sein.</span><span class="sxs-lookup"><span data-stu-id="deec1-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deec1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="deec1-117">Requirements</span></span>  
 <span data-ttu-id="deec1-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deec1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deec1-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="deec1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="deec1-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="deec1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="deec1-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deec1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
