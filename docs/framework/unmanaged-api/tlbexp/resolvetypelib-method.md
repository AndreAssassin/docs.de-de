---
title: ResolveTypeLib-Methode
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6db8925fb966f4a8b2a213b0d6e340d0edf107
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756430"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="c3a97-102">ResolveTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="c3a97-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="c3a97-103">Löst den einfachen Namen einer Typbibliothek durch den vollständig qualifizierten Pfad zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c3a97-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3a97-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3a97-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3a97-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="c3a97-106">[in] Ein [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , die den einfachen Namen der Typbibliothek enthält.</span><span class="sxs-lookup"><span data-stu-id="c3a97-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="c3a97-107">[in] Die GUID der Typbibliothek in der Registrierung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c3a97-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="c3a97-108">[in] Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c3a97-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="c3a97-109">[in] Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c3a97-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="c3a97-110">Z. B. für Version *x.y*, ist die Hauptversionsnummer *x*.</span><span class="sxs-lookup"><span data-stu-id="c3a97-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="c3a97-111">[in] Die Nebenversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c3a97-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="c3a97-112">Z. B. für Version *x.y*, ist die Nummer der Nebenversion *y*.</span><span class="sxs-lookup"><span data-stu-id="c3a97-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="c3a97-113">[in] Ein [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) Flag, das die betriebsumgebung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c3a97-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="c3a97-114">Häufig verwendete Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="c3a97-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="c3a97-115">[out] Ein Zeiger auf eine [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen in der `bstrSimpleName` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c3a97-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3a97-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3a97-116">Remarks</span></span>  
 <span data-ttu-id="c3a97-117">Die `ResolveTypeLib` Methode wird aufgerufen, indem die [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) während [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c3a97-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="c3a97-118">Benutzerdefinierte Implementierungen dieser Schnittstelle müssen Zurückgeben einer [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , enthält den vollständigen Pfad der Typbibliothek mit dem Namen in der `bstrSimpleName` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c3a97-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3a97-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3a97-119">Requirements</span></span>  
 <span data-ttu-id="c3a97-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3a97-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3a97-121">**Header:** TlbRef.idl, TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="c3a97-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="c3a97-122">**Bibliothek:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="c3a97-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="c3a97-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a97-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a97-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3a97-124">See also</span></span>

- [<span data-ttu-id="c3a97-125">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c3a97-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="c3a97-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="c3a97-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
