---
title: ServicePoint. m_ConnectionGroupList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1991dae4d03f617857b860f920077531f7937bf1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120047"
---
# <a name="servicepointm_connectiongrouplist-field"></a><span data-ttu-id="d9135-102">Service Point. m\_connectiongrouplist-Feld</span><span class="sxs-lookup"><span data-stu-id="d9135-102">ServicePoint.m\_ConnectionGroupList Field</span></span>

<span data-ttu-id="d9135-103">`ServicePoint.m_ConnectionGroupList` ist eine <xref:System.Collections.Hashtable> von Verbindungs Gruppen, die jeweils eine Verbindung für den URI des <xref:System.Net.ServicePoint>haben.</span><span class="sxs-lookup"><span data-stu-id="d9135-103">`ServicePoint.m_ConnectionGroupList` is a <xref:System.Collections.Hashtable> of connection groups, each holding a connection for the <xref:System.Net.ServicePoint>'s URI.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9135-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9135-104">Syntax</span></span>
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> <span data-ttu-id="d9135-105">Das `ServicePoint.m_ConnectionGroupList` Feld ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9135-105">The `ServicePoint.m_ConnectionGroupList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="d9135-106">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d9135-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9135-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9135-107">Requirements</span></span>

<span data-ttu-id="d9135-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d9135-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d9135-109">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="d9135-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d9135-110">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="d9135-110">**.NET Framework versions:** Available since 2.0.</span></span>
