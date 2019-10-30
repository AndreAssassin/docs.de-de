---
title: Connection. m_WriteList-Feld
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120031"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="e4579-102">Connection. m\_beschreitelist-Feld</span><span class="sxs-lookup"><span data-stu-id="e4579-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="e4579-103">`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekten, die in die Warteschlange eingereiht werden, um über HTTP gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="e4579-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4579-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4579-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="e4579-105">Das `Connection.m_WriteList` Feld ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4579-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="e4579-106">Microsoft unterstützt die Verwendung dieses Felds in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="e4579-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4579-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4579-107">Requirements</span></span>

<span data-ttu-id="e4579-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="e4579-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="e4579-109">**Assembly:** System (in "System. dll")</span><span class="sxs-lookup"><span data-stu-id="e4579-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="e4579-110">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="e4579-110">**.NET Framework versions:** Available since 2.0.</span></span>
