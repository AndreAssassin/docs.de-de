---
title: IAssemblyCacheItem::CreateStream-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98273307003485202d8c12d5c27fda04ff5a0ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629877"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="88d8f-102">IAssemblyCacheItem::CreateStream-Methode</span><span class="sxs-lookup"><span data-stu-id="88d8f-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="88d8f-103">Erstellt einen Datenstrom mit dem angegebenen Namen und Format.</span><span class="sxs-lookup"><span data-stu-id="88d8f-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="88d8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88d8f-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="88d8f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="88d8f-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="88d8f-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="88d8f-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="88d8f-107">[in] Der Name des zu erstellenden Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="88d8f-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="88d8f-108">[in] Das Format der Datei, die gestreamt werden.</span><span class="sxs-lookup"><span data-stu-id="88d8f-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="88d8f-109">[in] Formatspezifische-Flags in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="88d8f-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="88d8f-110">[out] Ein Zeiger auf die Adresse des zurückgegebenen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Instanz.</span><span class="sxs-lookup"><span data-stu-id="88d8f-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="88d8f-111">[in, optional] Die maximale Größe des Streams verweist `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="88d8f-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="88d8f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88d8f-112">Requirements</span></span>

<span data-ttu-id="88d8f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88d8f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="88d8f-114">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="88d8f-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="88d8f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88d8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="88d8f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88d8f-116">See also</span></span>

- [<span data-ttu-id="88d8f-117">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88d8f-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
