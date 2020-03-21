---
title: ServicePointManager.s_ServicePointTable-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155812"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="f25c5-102">ServicePointManager.s\_ServicePointTable-Feld</span><span class="sxs-lookup"><span data-stu-id="f25c5-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="f25c5-103">`ServicePointManager.s_ServicePointTable`ist <xref:System.Collections.Hashtable> eine, die die Liste<xref:System.Net.ServicePoint>der aktiven <xref:System.AppDomain>HTTP-Verbindungen (s) im enthält.</span><span class="sxs-lookup"><span data-stu-id="f25c5-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="f25c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f25c5-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="f25c5-105">Das `ServicePointManager.s_ServicePointTable` Feld ist privat und soll nicht direkt in Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f25c5-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f25c5-106">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="f25c5-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f25c5-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f25c5-107">Requirements</span></span>

<span data-ttu-id="f25c5-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f25c5-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f25c5-109">**Montage:** System (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="f25c5-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f25c5-110">**.NET Framework-Versionen:** Verfügbar seit 2.0.</span><span class="sxs-lookup"><span data-stu-id="f25c5-110">**.NET Framework versions:** Available since 2.0.</span></span>
