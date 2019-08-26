---
title: '#elif – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: b04db4bd23a459043efec59b8ebf9d322defbcf7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608583"
---
# <a name="elif-c-reference"></a><span data-ttu-id="bb06e-102">#elif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bb06e-102">#elif (C# Reference)</span></span>
<span data-ttu-id="bb06e-103">Mit `#elif` können zusammengesetzte bedingte Direktiven erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bb06e-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="bb06e-104">Der `#elif`-Ausdruck wird ausgewertet, wenn weder der Ausdruck der vorangehenden [#if](./preprocessor-if.md)-Anweisung noch der Ausdruck einer vorangehenden optionalen `#elif`-Anweisung zu `true` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="bb06e-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="bb06e-105">Wenn ein `#elif`-Ausdruck zu `true` ausgewertet wird, wird der gesamte Code zwischen der `#elif`-Direktive und der nächsten bedingten Direktive vom Compiler ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="bb06e-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="bb06e-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb06e-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="bb06e-107">Die Operatoren `==` (Gleichheit), `!=` (Ungleichheit), `&&` (und) und `||` (oder) können zur Auswertung mehrerer Symbole verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb06e-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="bb06e-108">Symbole und Operatoren können auch mit Klammern gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb06e-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb06e-109">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="bb06e-109">Remarks</span></span>  
 <span data-ttu-id="bb06e-110">`#elif` ist identisch mit der Verwendung von:</span><span class="sxs-lookup"><span data-stu-id="bb06e-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="bb06e-111">Die Verwendung von `#elif` ist einfacher, da für jedes `#if` ein [#endif](./preprocessor-endif.md) erforderlich ist, während ein `#elif` ohne ein entsprechendes `#endif` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb06e-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="bb06e-112">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#elif`.</span><span class="sxs-lookup"><span data-stu-id="bb06e-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb06e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb06e-113">See also</span></span>

- [<span data-ttu-id="bb06e-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bb06e-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bb06e-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bb06e-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bb06e-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="bb06e-116">C# Preprocessor Directives</span></span>](./index.md)
