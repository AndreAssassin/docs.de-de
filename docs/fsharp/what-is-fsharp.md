---
title: Was ist F#
description: Erfahren Sie, was der F#-Programmiersprache und F#-Programmierung wie. Informationen Sie zu Datentypen, Funktionen und deren Zusammenwirken.
ms.date: 08/03/2018
ms.openlocfilehash: 9d5b0de9828aa91857d3961bf7d40c02c344adaa
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641575"
---
# <a name="what-is-f"></a><span data-ttu-id="71922-104">Was ist F\#</span><span class="sxs-lookup"><span data-stu-id="71922-104">What is F\#</span></span>

<span data-ttu-id="71922-105">F#ist eine funktionale Programmiersprache, die es einfach macht, die richtigen und verwaltbaren Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="71922-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="71922-106">F#Programmieren in erster Linie umfasst das Definieren von Typen und Funktionen, die automatisch generalisiert und Typ abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="71922-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="71922-107">Dadurch können sich der Fokus auf der Problemdomäne und bearbeiten die Details der Programmierung, anstatt die Daten verbleiben.</span><span class="sxs-lookup"><span data-stu-id="71922-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="71922-108">F#verfügt über zahlreiche Features, darunter:</span><span class="sxs-lookup"><span data-stu-id="71922-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="71922-109">Einfache syntax</span><span class="sxs-lookup"><span data-stu-id="71922-109">Lightweight syntax</span></span>
* <span data-ttu-id="71922-110">Standardmäßig unveränderlich</span><span class="sxs-lookup"><span data-stu-id="71922-110">Immutable by default</span></span>
* <span data-ttu-id="71922-111">Typrückschluss und automatische Verallgemeinerung</span><span class="sxs-lookup"><span data-stu-id="71922-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="71922-112">Funktionen</span><span class="sxs-lookup"><span data-stu-id="71922-112">First-class functions</span></span>
* <span data-ttu-id="71922-113">Leistungsstarke-Datentypen</span><span class="sxs-lookup"><span data-stu-id="71922-113">Powerful data types</span></span>
* <span data-ttu-id="71922-114">Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="71922-114">Pattern matching</span></span>
* <span data-ttu-id="71922-115">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="71922-115">Async programming</span></span>

<span data-ttu-id="71922-116">Ein vollständiger Satz von Features sind in dokumentiert die [ F# Sprachreferenz](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="71922-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="71922-117">Rich-Datentypen</span><span class="sxs-lookup"><span data-stu-id="71922-117">Rich data types</span></span>

<span data-ttu-id="71922-118">Datentypen wie [Datensätze](language-reference/records.md) und [Unterscheidungs-Unions](language-reference/discriminated-unions.md) können Sie komplexe Daten und Domänen darstellen.</span><span class="sxs-lookup"><span data-stu-id="71922-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="71922-119">F#Datensätze und Unterscheidungs-Unions sind ungleich Null, unveränderliche und vergleichbare standardmäßig, sodass sie sehr einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="71922-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="71922-120">Erzwungene Richtigkeit mit Funktionen und des musterabgleichs</span><span class="sxs-lookup"><span data-stu-id="71922-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="71922-121">F#Funktionen sind einfach zu deklarieren und leistungsstarke in der Praxis.</span><span class="sxs-lookup"><span data-stu-id="71922-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="71922-122">In Kombination mit [Musterabgleich](language-reference/pattern-matching.md), können Sie sich zur Verhalten definieren, deren Richtigkeit wird vom Compiler erzwungen.</span><span class="sxs-lookup"><span data-stu-id="71922-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="71922-123">F#Funktionen sind auch erstklassige, d. h., sie als Parameter übergeben und von anderen Funktionen zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="71922-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="71922-124">Funktionen, um Vorgänge für Objekte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="71922-124">Functions to define operations on objects</span></span>

<span data-ttu-id="71922-125">F#bietet vollständige Unterstützung für Objekte, die nützliche Daten-Typen sind, wenn Sie Daten und Funktionen in blend müssen.</span><span class="sxs-lookup"><span data-stu-id="71922-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="71922-126">F#Funktionen werden verwendet, um Objekte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="71922-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="71922-127">Anstatt das Schreiben von Code, der objektorientiert, in F# ist, Schreiben häufig Sie Code, die behandelt werden, wie ein anderer Datentyp für die Funktionen zum Bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="71922-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="71922-128">Funktionen, z. B. [generische Schnittstellen](language-reference/interfaces.md), [Objektausdrücke](language-reference/object-expressions.md), und zielgerichtete Verwendung von [Mitglieder](language-reference/members/index.md) werden häufig in größeren F# Programme.</span><span class="sxs-lookup"><span data-stu-id="71922-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="71922-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="71922-129">Next steps</span></span>

<span data-ttu-id="71922-130">Weitere Informationen zu einem größeren Satz F# Features sehen Sie sich die [ F# Tour](tour.md).</span><span class="sxs-lookup"><span data-stu-id="71922-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
