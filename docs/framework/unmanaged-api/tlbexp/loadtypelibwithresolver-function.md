---
title: LoadTypeLibWithResolver-Funktion
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c14080e3ac128a6a7fbb48586f59d8a5ea4105f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049335"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="e6603-102">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="e6603-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="e6603-103">Lädt eine Typbibliothek und verwendet die angegebene [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) intern referenzierte Typbibliotheken aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="e6603-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6603-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6603-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6603-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6603-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="e6603-106">[in] Der Dateipfad der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="e6603-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="e6603-107">[in] Ein [REGKIND Enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) Flag, das steuert, wie die Typbibliothek registriert wird.</span><span class="sxs-lookup"><span data-stu-id="e6603-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="e6603-108">Die Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="e6603-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="e6603-109">`REGKIND_DEFAULT`: Verwenden Sie Standardverhalten für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e6603-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="e6603-110">`REGKIND_REGISTER`: Diese Typbibliothek zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="e6603-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="e6603-111">`REGKIND_NONE`: Führen Sie diese Typbibliothek nicht registriert werden.</span><span class="sxs-lookup"><span data-stu-id="e6603-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="e6603-112">[in] Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e6603-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="e6603-113">[out] Ein Verweis auf die Typbibliothek, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e6603-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6603-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6603-114">Return Value</span></span>  
 <span data-ttu-id="e6603-115">Einer der in der folgenden Tabelle aufgeführten HRESULT-Werte.</span><span class="sxs-lookup"><span data-stu-id="e6603-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="e6603-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6603-116">Return value</span></span>|<span data-ttu-id="e6603-117">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="e6603-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="e6603-118">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e6603-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="e6603-119">Nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e6603-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="e6603-120">Eine oder mehrere der Zeiger sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="e6603-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="e6603-121">Eine oder mehrere der Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="e6603-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="e6603-122">Die Funktion konnte nicht in die Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="e6603-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="e6603-123">Die Systemdatenbank für die Registrierung konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="e6603-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="e6603-124">Die Typbibliothek konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="e6603-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="e6603-125">Die Typbibliothek oder einer DLL konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e6603-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6603-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6603-126">Remarks</span></span>  
 <span data-ttu-id="e6603-127">Die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) Aufrufe der `LoadTypeLibWithResolver` Funktion während der Konvertierung der Assembly in den Typ in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="e6603-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="e6603-128">Diese Funktion lädt die angegebene Typbibliothek mit minimalen Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e6603-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="e6603-129">Die Funktion überprüft dann die Typbibliothek für Typbibliotheken intern auf die verwiesen wird, von die jede geladen und der übergeordnete Typ-Bibliothek hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="e6603-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="e6603-130">Bevor eine referenzierte Typbibliothek geladen werden kann, muss die Verweis-Dateipfad in einen vollständigen Dateipfad aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e6603-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="e6603-131">Dies erfolgt über die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , erfolgt über die [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), im übergeben wird die `pTlbResolver` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e6603-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="e6603-132">Wenn Sie der vollständigen Pfad der Typbibliothek, auf die verwiesen wird, bekannt ist, die `LoadTypeLibWithResolver` Funktion lädt und die Bibliothek mit übergeordneten, erstellen eine kombinierte master Typbibliothek die referenzierte Bibliothek hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6603-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="e6603-133">Nachdem die Funktion aufgelöst und alle intern Typbibliotheken lädt, gibt es einen Verweis auf master aufgelöst Typbibliothek in der `pptlib` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e6603-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="e6603-134">Die `LoadTypeLibWithResolver` Funktion ist in der Regel aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), die stellt eine eigene, interne [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) -Implementierung in der `pTlbResolver` der Parameter.</span><span class="sxs-lookup"><span data-stu-id="e6603-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="e6603-135">Wenn Sie aufrufen `LoadTypeLibWithResolver` direkt, geben Sie an Ihre eigenen [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) Implementierung.</span><span class="sxs-lookup"><span data-stu-id="e6603-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6603-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6603-136">Requirements</span></span>  
 <span data-ttu-id="e6603-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6603-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6603-138">**Header:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="e6603-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="e6603-139">**Bibliothek:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="e6603-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="e6603-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="e6603-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6603-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6603-141">See also</span></span>

- [<span data-ttu-id="e6603-142">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="e6603-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="e6603-143">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="e6603-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
