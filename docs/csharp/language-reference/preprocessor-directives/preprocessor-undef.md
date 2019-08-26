---
title: '#undef – C#-Referenz'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: fdf22e90be766e87e823a7f8cc27ea00c17d2bb5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605583"
---
# <a name="undef-c-reference"></a><span data-ttu-id="e3141-102">#undef (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e3141-102">#undef (C# Reference)</span></span>
<span data-ttu-id="e3141-103">Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](./preprocessor-if.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e3141-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="e3141-104">Ein Symbol kann entweder mit der Anweisung [#define](./preprocessor-define.md) oder der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3141-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e3141-105">Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.</span><span class="sxs-lookup"><span data-stu-id="e3141-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3141-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3141-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="e3141-107">**DEBUG ist nicht definiert**</span><span class="sxs-lookup"><span data-stu-id="e3141-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="e3141-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3141-108">See also</span></span>

- [<span data-ttu-id="e3141-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e3141-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3141-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e3141-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e3141-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="e3141-111">C# Preprocessor Directives</span></span>](./index.md)
