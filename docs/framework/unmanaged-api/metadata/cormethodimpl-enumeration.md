---
title: CorMethodImpl-Enumeration
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2138dd32cf39db7b7c8989ba5827178d1a1e46c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117234"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="b2ee0-102">CorMethodImpl-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b2ee0-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="b2ee0-103">Enthält Werte, die Funktionen zur Implementierung von Methoden beschreiben.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ee0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2ee0-104">Syntax</span></span>  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="b2ee0-105">Member</span><span class="sxs-lookup"><span data-stu-id="b2ee0-105">Members</span></span>  
  
|<span data-ttu-id="b2ee0-106">Member</span><span class="sxs-lookup"><span data-stu-id="b2ee0-106">Member</span></span>|<span data-ttu-id="b2ee0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2ee0-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="b2ee0-108">Flags, die Codetyp beschreiben.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="b2ee0-109">Gibt an, dass die methodenimplementierung Microsoft intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="b2ee0-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="b2ee0-110">Gibt an, dass die Methodenimplementierung nativ ist.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="b2ee0-111">Gibt an, dass die methodenimplementierung OPTIL.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="b2ee0-112">Gibt an, dass die methodenimplementierung von der common Language Runtime bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="b2ee0-113">Flags, die angibt, ob der Code verwaltet oder nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="b2ee0-114">Gibt an, dass die methodenimplementierung nicht verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="b2ee0-115">Gibt an, dass die methodenimplementierung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="b2ee0-116">Gibt an, dass die Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-116">Specifies that the method is defined.</span></span> <span data-ttu-id="b2ee0-117">Dieses Flag wird in erster Linie in der Merge-Szenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="b2ee0-118">Gibt an, dass die Signatur der Methode für eine Konvertierung von HRESULT nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="b2ee0-119">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="b2ee0-120">Gibt an, dass die Methode mit Textkörpers Single-Thread.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="b2ee0-121">Gibt an, dass die Methode nicht intern sein kann.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="b2ee0-122">Gibt an, dass die Methode nach Möglichkeit intern sein sollte.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="b2ee0-123">Gibt an, dass die Methode nicht optimiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="b2ee0-124">Der gültige Höchstwert für eine `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="b2ee0-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2ee0-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2ee0-125">Requirements</span></span>  
 <span data-ttu-id="b2ee0-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2ee0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ee0-127">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b2ee0-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b2ee0-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ee0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ee0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2ee0-129">See also</span></span>

- [<span data-ttu-id="b2ee0-130">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b2ee0-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
