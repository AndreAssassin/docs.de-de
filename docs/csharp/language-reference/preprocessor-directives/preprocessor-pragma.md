---
title: '#pragma – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712454"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3a282-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3a282-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="3a282-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="3a282-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3a282-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3a282-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3a282-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a282-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3a282-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="3a282-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3a282-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3a282-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3a282-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3a282-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3a282-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a282-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a282-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a282-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="3a282-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3a282-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3a282-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="3a282-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a282-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a282-113">See also</span></span>

- [<span data-ttu-id="3a282-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3a282-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a282-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3a282-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a282-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="3a282-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="3a282-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3a282-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="3a282-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3a282-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
