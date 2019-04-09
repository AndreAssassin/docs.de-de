---
title: USER_THREAD-Struktur
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127154"
---
# <a name="userthread-structure"></a><span data-ttu-id="0e9ef-102">USER_THREAD-Struktur</span><span class="sxs-lookup"><span data-stu-id="0e9ef-102">USER_THREAD Structure</span></span>
<span data-ttu-id="0e9ef-103">Enthält Informationen für einen Debugger über einen Thread.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="0e9ef-104">Weitere Informationen finden Sie unter den [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e9ef-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="0e9ef-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e9ef-106">Members</span></span>  
  
|<span data-ttu-id="0e9ef-107">Member</span><span class="sxs-lookup"><span data-stu-id="0e9ef-107">Member</span></span>|<span data-ttu-id="0e9ef-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e9ef-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="0e9ef-109">Die Adresse des Threadpuffers.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="0e9ef-110">Länge des Threadpuffers in Byte.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="0e9ef-111">Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e9ef-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e9ef-112">Requirements</span></span>  
 <span data-ttu-id="0e9ef-113">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0e9ef-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9ef-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e9ef-114">See also</span></span>

- [<span data-ttu-id="0e9ef-115">SetNotifyFilter-Methode</span><span class="sxs-lookup"><span data-stu-id="0e9ef-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="0e9ef-116">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="0e9ef-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
