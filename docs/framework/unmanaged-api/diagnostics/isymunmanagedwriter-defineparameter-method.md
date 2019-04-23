---
title: ISymUnmanagedWriter::DefineParameter-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0fb35f5d7fec0c79a31cd8d7b77cf2b1c043f60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148017"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="2c331-102">ISymUnmanagedWriter::DefineParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="2c331-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="2c331-103">Definiert einen einzelnen Parameter in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="2c331-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="2c331-104">Der Parametertyp stammt aus der die Position des Parameters (Sequenz) in der Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="2c331-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="2c331-105">Wenn Parameter in den Metadaten für eine bestimmte Methode definiert sind, müssen Sie nicht erneut mit dieser Methode definieren.</span><span class="sxs-lookup"><span data-stu-id="2c331-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="2c331-106">Die Symbolreader müssen den normalen Metadaten für die Parameter vor dem Überprüfen des Symbolspeichers überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2c331-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c331-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c331-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c331-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c331-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2c331-109">[in] Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="2c331-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="2c331-110">[in] Die Parameterattribute.</span><span class="sxs-lookup"><span data-stu-id="2c331-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="2c331-111">[in] Die Parametersignatur.</span><span class="sxs-lookup"><span data-stu-id="2c331-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="2c331-112">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="2c331-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="2c331-113">[in] Die erste Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="2c331-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="2c331-114">[in] Die zweite Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="2c331-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="2c331-115">[in] Die dritte Adresse für die Parameterangabe.</span><span class="sxs-lookup"><span data-stu-id="2c331-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c331-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c331-116">Return Value</span></span>  
 <span data-ttu-id="2c331-117">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2c331-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c331-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c331-118">Requirements</span></span>  
 <span data-ttu-id="2c331-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2c331-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c331-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c331-120">See also</span></span>

- [<span data-ttu-id="2c331-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c331-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
