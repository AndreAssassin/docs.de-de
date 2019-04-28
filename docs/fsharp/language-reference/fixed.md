---
title: Das fixed-Schlüsselwort
description: Erfahren Sie, wie Sie "pin" eine lokale im Stapel, um zu verhindern, dass bei der Sammlung mit den F# 'fixed'-Schlüsselwort.
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772657"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="44c5d-103">Das fixed-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="44c5d-103">The fixed keyword</span></span>

<span data-ttu-id="44c5d-104">F#4.1 führt die `fixed` -Schlüsselwort, das Ihnen ermöglicht, eine lokale im Stapel, um zu verhindern, dass es gesammelt oder während der Garbage Collection verschoben "anheften".</span><span class="sxs-lookup"><span data-stu-id="44c5d-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="44c5d-105">Sie wird für Low-Level Programmierszenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="44c5d-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="44c5d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="44c5d-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="44c5d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44c5d-107">Remarks</span></span>

<span data-ttu-id="44c5d-108">Dadurch wird die Syntax von Ausdrücken können Sie einen Zeiger zu extrahieren und binden Sie ihn in einen Namen verhindert gesammelt oder während der Garbage Collection verschoben wird, erweitert.</span><span class="sxs-lookup"><span data-stu-id="44c5d-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="44c5d-109">Ein Zeiger von einem Ausdruck wurde behoben, über die `fixed` Schlüsselwort gebunden ist, auf einen Bezeichner über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="44c5d-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="44c5d-110">Die Semantik dieser ähneln denen auf die ressourcenverwaltung, über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="44c5d-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="44c5d-111">Der Zeiger wurde behoben, während er im Gültigkeitsbereich befindet, und sobald sie außerhalb des gültigen Bereichs ist, ist es nicht mehr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44c5d-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="44c5d-112">`fixed` kann nicht verwendet werden, außerhalb des Kontexts einer `use` Bindung.</span><span class="sxs-lookup"><span data-stu-id="44c5d-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="44c5d-113">Sie müssen den Zeiger in einen Namen mit binden `use`.</span><span class="sxs-lookup"><span data-stu-id="44c5d-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="44c5d-114">Verwenden von `fixed` muss innerhalb eines Ausdrucks zu einer Funktion oder Methode erfolgen.</span><span class="sxs-lookup"><span data-stu-id="44c5d-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="44c5d-115">Es kann nicht in einem Skript auf Serverebene oder auf Modulebene Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44c5d-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="44c5d-116">Wie alle Zeiger-Code Dies ist eine unsichere-Funktion und gibt eine Warnung generiert wird.</span><span class="sxs-lookup"><span data-stu-id="44c5d-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="44c5d-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44c5d-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="44c5d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44c5d-118">See also</span></span>

- [<span data-ttu-id="44c5d-119">NativePtr-Modul</span><span class="sxs-lookup"><span data-stu-id="44c5d-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
