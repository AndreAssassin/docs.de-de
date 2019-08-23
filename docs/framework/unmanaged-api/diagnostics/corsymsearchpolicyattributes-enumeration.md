---
title: CorSymSearchPolicyAttributes-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7188c516d3d0a5192251697ec743e9d41f8d9072
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913744"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="b4aa3-102">CorSymSearchPolicyAttributes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b4aa3-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="b4aa3-103">Gibt die Richtlinie an, die bei einer Suche nach einem Symbol Leser verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="b4aa3-104">Diese Konstanten werden von der [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) -Methode und der [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b4aa3-105">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4aa3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4aa3-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="b4aa3-107">Member</span><span class="sxs-lookup"><span data-stu-id="b4aa3-107">Members</span></span>  
  
|<span data-ttu-id="b4aa3-108">Member</span><span class="sxs-lookup"><span data-stu-id="b4aa3-108">Member</span></span>|<span data-ttu-id="b4aa3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4aa3-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="b4aa3-110">Fragt die Registrierung nach Symbol Suchpfaden ab.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="b4aa3-111">Greift auf einen Symbol Server zu.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="b4aa3-112">Durchsucht den im Debug-Verzeichnis angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="b4aa3-113">Sucht die PDB an der Stelle, an der die exe-Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b4aa3-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4aa3-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4aa3-114">Requirements</span></span>  
 <span data-ttu-id="b4aa3-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4aa3-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4aa3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4aa3-116">See also</span></span>

- [<span data-ttu-id="b4aa3-117">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b4aa3-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
