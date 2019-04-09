---
title: StackTrace_SimpleContext-Struktur
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210424"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="5cc3b-102">StackTrace_SimpleContext-Struktur</span><span class="sxs-lookup"><span data-stu-id="5cc3b-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="5cc3b-103">Stellt einen einfachen Kontext bereit, der statt einer vollständigen `CONTEXT`-Struktur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5cc3b-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cc3b-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="5cc3b-105">Member</span><span class="sxs-lookup"><span data-stu-id="5cc3b-105">Members</span></span>  
  
|<span data-ttu-id="5cc3b-106">Member</span><span class="sxs-lookup"><span data-stu-id="5cc3b-106">Member</span></span>|<span data-ttu-id="5cc3b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cc3b-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="5cc3b-108">Der Stapelzeiger oder der EINGABETASTE Stapelzeiger (ESP) auf X86 Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5cc3b-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="5cc3b-109">Die Frameoffset oder die EBP-Register auf X86 Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5cc3b-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="5cc3b-110">Der Anweisungszeiger oder der EINGABETASTE Anweisungszeiger (EIP) auf X86 Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5cc3b-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cc3b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5cc3b-111">Remarks</span></span>  
 <span data-ttu-id="5cc3b-112">Da die Funktionen der Aufrufliste-Ablaufverfolgung in der Regel nur die Adresse, Frameoffset und Stapeladresse zurückgeben müssen, können Sie optional mithilfe der `SimpleContext` Struktur anstelle einer großen `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="5cc3b-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc3b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cc3b-113">Requirements</span></span>  
 <span data-ttu-id="5cc3b-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc3b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc3b-115">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="5cc3b-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="5cc3b-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5cc3b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cc3b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cc3b-117">See also</span></span>

- [<span data-ttu-id="5cc3b-118">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="5cc3b-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="5cc3b-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5cc3b-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
