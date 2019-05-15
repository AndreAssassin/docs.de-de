---
title: Ergebnisse
description: Erfahren Sie, wie Sie mit der F# "Result" Geben Sie fehlertoleranten Code schreiben können.
ms.date: 04/24/2017
ms.openlocfilehash: 36f60df8a2991c1d318e4921af6c9e89a0156918
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645324"
---
# <a name="results"></a>Ergebnisse

Ab F# 4.1, es ist ein `Result<'T,'TFailure>` geben, die Sie verwenden können, für das Schreiben von fehlertoleranten Code, der zusammengesetzt werden kann.

## <a name="syntax"></a>Syntax

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Hinweise

Beachten Sie, dass der Rückgabetyp einer [diskriminierte Union](discriminated-unions.md#struct-discriminated-unions), dies ist ein weiteres Feature, die in F# 4.1 eingeführt.  Strukturelle Gleichheitssemantik gelten hier.

Die `Result` Typ wird normalerweise verwendet, bei der monadische-Fehlerbehandlung, die häufig als bezeichnet wird [Eisenbahn objektorientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) innerhalb der F# Community.  Das folgende einfache Beispiel veranschaulicht diesen Ansatz.

```fsharp
// Define a simple type which has fields that can be validated
type Request = 
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

Wie Sie sehen können, ist es recht einfach, verschiedene Validierungsfunktionen miteinander zu verketten, wenn Sie sie alle zurückgeben Erzwingen einer `Result`.  So können Sie Funktionen wie folgt in kleine Teile aufteilen sind als zusammensetzbar, wie Sie diese benötigen.  Dies hat auch dem Mehrwert des *erzwingen* die Verwendung von [Musterabgleich](pattern-matching.md) am Ende einer Rundung der Überprüfung, das wiederum ein höheres Maß an Richtigkeit des Programms erzwingt.

## <a name="see-also"></a>Siehe auch

- [Unterscheidbare Unions](discriminated-unions.md)
- [Mustervergleich](pattern-matching.md)
