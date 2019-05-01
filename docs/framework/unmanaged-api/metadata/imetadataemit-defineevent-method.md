---
title: IMetaDataEmit::DefineEvent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48055103b49b4c61bb7561f2d4aa6c8daae07ae2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044212"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="eb4cd-102">IMetaDataEmit::DefineEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="eb4cd-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="eb4cd-103">Erstellt eine Definition für ein Ereignis mit der angegebenen Metadaten-Signatur und ruft ein Token für die Ereignisdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb4cd-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb4cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb4cd-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="eb4cd-106">[in] Das Token für die Zielklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="eb4cd-107">Dies ist entweder ein `mdTypeDef` oder `mdTypeDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="eb4cd-108">[in] Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="eb4cd-109">[in] Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="eb4cd-110">[in] Das Token für Event-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-110">[in] The token for the event class.</span></span> <span data-ttu-id="eb4cd-111">Dies ist eine `mdTypeDef`, `mdTypeRef`, oder ein `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="eb4cd-112">[in] Die Methode, die zum Abonnieren das Ereignis oder Null.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="eb4cd-113">[in] Die Methode verwendet, um das Ereignis oder Null zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="eb4cd-114">[in] Die Methode, die zum Auslösen des Ereignisses (durch eine abgeleitete Klasse) verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="eb4cd-115">[in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="eb4cd-116">Das Array wird mit beendet eine `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="eb4cd-117">[out] Das Metadatentoken, das dem Ereignis zugewiesenen.</span><span class="sxs-lookup"><span data-stu-id="eb4cd-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb4cd-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb4cd-118">Requirements</span></span>  
 <span data-ttu-id="eb4cd-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb4cd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb4cd-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb4cd-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb4cd-121">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="eb4cd-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb4cd-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb4cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4cd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb4cd-123">See also</span></span>

- [<span data-ttu-id="eb4cd-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb4cd-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="eb4cd-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb4cd-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
