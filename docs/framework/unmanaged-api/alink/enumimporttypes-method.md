---
title: EnumImportTypes-Methode
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789954"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="c8fe8-102">EnumImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="c8fe8-102">EnumImportTypes Method</span></span>

<span data-ttu-id="c8fe8-103">Listet jeden Typ in jedem Bereich an.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8fe8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8fe8-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="c8fe8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8fe8-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="c8fe8-106">Handle für Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="c8fe8-107">Maximale Anzahl von Typen, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="c8fe8-108">Typtoken, nicht zu überschreiten erhält `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="c8fe8-109">Empfängt die tatsächliche Anzahl der Typen in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c8fe8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8fe8-110">Return Value</span></span>

<span data-ttu-id="c8fe8-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c8fe8-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8fe8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8fe8-112">Requirements</span></span>

<span data-ttu-id="c8fe8-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="c8fe8-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="c8fe8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8fe8-114">See also</span></span>

- [<span data-ttu-id="c8fe8-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8fe8-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c8fe8-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8fe8-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c8fe8-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c8fe8-117">ALink API</span></span>](index.md)