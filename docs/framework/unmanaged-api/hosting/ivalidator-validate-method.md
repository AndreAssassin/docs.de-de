---
title: IValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127503"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="2851b-102">IValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="2851b-102">IValidator::Validate Method</span></span>
<span data-ttu-id="2851b-103">Überprüft die angegebene Datei (portable Executable) oder Microsoft intermediate Language (MSIL)-Datei.</span><span class="sxs-lookup"><span data-stu-id="2851b-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2851b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2851b-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2851b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2851b-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="2851b-106">[in] Ein Zeiger auf ein `IVEHandler` -Instanz, die Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="2851b-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="2851b-107">[in] Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="2851b-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="2851b-108">[in] Eine bitweise Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der angibt, Überprüfungen, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2851b-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="2851b-109">[in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Überprüfungsprozess zulassen.</span><span class="sxs-lookup"><span data-stu-id="2851b-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="2851b-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2851b-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="2851b-111">[in] Eine Zeichenfolge, die mit dem Namen der Datei, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="2851b-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="2851b-112">[in] Ein Zeiger auf den Speicherpuffer, die in dem die Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2851b-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="2851b-113">[in] Die Größe in Bytes der Datei, die überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2851b-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2851b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2851b-114">Requirements</span></span>  
 <span data-ttu-id="2851b-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2851b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2851b-116">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="2851b-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="2851b-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2851b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2851b-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2851b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
