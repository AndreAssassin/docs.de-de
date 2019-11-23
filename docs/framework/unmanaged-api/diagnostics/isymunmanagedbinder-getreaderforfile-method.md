---
title: ISymUnmanagedBinder::GetReaderForFile-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
ms.openlocfilehash: 94cda16466ea5a3d35a478a2ae80281e9414f719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449361"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="d50e7-102">ISymUnmanagedBinder::GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="d50e7-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="d50e7-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span><span class="sxs-lookup"><span data-stu-id="d50e7-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="d50e7-104">This method will open the program database (PDB) file only if it is next to the executable file.</span><span class="sxs-lookup"><span data-stu-id="d50e7-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="d50e7-105">This change has been made for security purposes.</span><span class="sxs-lookup"><span data-stu-id="d50e7-105">This change has been made for security purposes.</span></span> <span data-ttu-id="d50e7-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="d50e7-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d50e7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d50e7-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d50e7-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d50e7-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="d50e7-109">[in] A pointer to the metadata import interface.</span><span class="sxs-lookup"><span data-stu-id="d50e7-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d50e7-110">[in] A pointer to the file name.</span><span class="sxs-lookup"><span data-stu-id="d50e7-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="d50e7-111">[in] A pointer to the search path.</span><span class="sxs-lookup"><span data-stu-id="d50e7-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d50e7-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="d50e7-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d50e7-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d50e7-113">Return Value</span></span>  
 <span data-ttu-id="d50e7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d50e7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d50e7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d50e7-115">Requirements</span></span>  
 <span data-ttu-id="d50e7-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d50e7-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50e7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d50e7-117">See also</span></span>

- [<span data-ttu-id="d50e7-118">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d50e7-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="d50e7-119">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="d50e7-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
