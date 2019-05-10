---
title: F#Richtlinien für die codeformatierung
description: Erfahren Sie, Richtlinien für die Formatierung F# Code.
ms.date: 02/08/2019
ms.openlocfilehash: ce07bd800984ec082a522bc62cb487f786fa0510
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063606"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="68490-103">F#Richtlinien für die codeformatierung</span><span class="sxs-lookup"><span data-stu-id="68490-103">F# code formatting guidelines</span></span>

<span data-ttu-id="68490-104">Dieser Artikel bietet Richtlinien für Ihren Code zu formatieren, damit Ihre F# Code ist:</span><span class="sxs-lookup"><span data-stu-id="68490-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="68490-105">In der Regel als besser lesbar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68490-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="68490-106">In Übereinstimmung mit Konventionen formatiert-Tools in Visual Studio und andere Editoren angewendet wird</span><span class="sxs-lookup"><span data-stu-id="68490-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="68490-107">Ähnlich wie bei anderen Code online</span><span class="sxs-lookup"><span data-stu-id="68490-107">Similar to other code online</span></span>

<span data-ttu-id="68490-108">Diese Leitlinien basieren auf [ein umfassendes Handbuch zum F# Formatierungskonventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="68490-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="68490-109">Allgemeine Regeln für den Einzug</span><span class="sxs-lookup"><span data-stu-id="68490-109">General rules for indentation</span></span>

<span data-ttu-id="68490-110">F#signifikanten Leerraum wird standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="68490-110">F# uses significant white space by default.</span></span> <span data-ttu-id="68490-111">Die folgenden Richtlinien dienen bieten eine Anleitung, wie einige Herausforderungen unter einen Hut bringen, die diese darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="68490-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="68490-112">Mithilfe von Speicherplätzen</span><span class="sxs-lookup"><span data-stu-id="68490-112">Using spaces</span></span>

<span data-ttu-id="68490-113">Wenn der Einzug erforderlich ist, müssen Sie Leerzeichen nicht Registerkarten verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="68490-114">Mindestens ein Leerzeichen ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="68490-114">At least one space is required.</span></span> <span data-ttu-id="68490-115">Ihre Organisation kann zum Angeben der Anzahl der Leerzeichen für Einzüge zu verwendende Codierungsstandards erstellen; zwei, drei oder vier Leerzeichen des Einzugs am jede Einzugsebene ist typisch.</span><span class="sxs-lookup"><span data-stu-id="68490-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="68490-116">**Es wird empfohlen, 4 Leerzeichen pro Einzug.**</span><span class="sxs-lookup"><span data-stu-id="68490-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="68490-117">Dies bedeutet, dass der Einzug der Programme eine subjektive Angelegenheit ist.</span><span class="sxs-lookup"><span data-stu-id="68490-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="68490-118">Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten ist *Konsistenz des Einzugs*.</span><span class="sxs-lookup"><span data-stu-id="68490-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="68490-119">Wählen Sie ein allgemein anerkannten Format des Einzugs und systematisch in Ihrer gesamten Codebasis verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="68490-120">Formatieren von Leerraum</span><span class="sxs-lookup"><span data-stu-id="68490-120">Formatting white space</span></span>

<span data-ttu-id="68490-121">F#wird Sie Leerzeichen beachtet.</span><span class="sxs-lookup"><span data-stu-id="68490-121">F# is white space sensitive.</span></span> <span data-ttu-id="68490-122">Obwohl die meisten Semantik von Leerzeichen durch richtige Einzugs abgedeckt werden, gibt es einige andere Dinge zu beachten.</span><span class="sxs-lookup"><span data-stu-id="68490-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="68490-123">Formatieren von Operatoren in arithmetischen Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="68490-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="68490-124">Verwenden Sie immer Leerzeichen um binäre arithmetische Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="68490-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="68490-125">Unäre `-` Operatoren müssen immer den Wert, der sie negiert werden unmittelbar folgen:</span><span class="sxs-lookup"><span data-stu-id="68490-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="68490-126">Ein Leerzeichen nach dem Hinzufügen der `-` Operator kann zu Verwirrung führen, für andere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="68490-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="68490-127">Zusammenfassend lässt sich sagen ist es wichtig, immer:</span><span class="sxs-lookup"><span data-stu-id="68490-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="68490-128">Binäre Operatoren mit Leerraum umgeben</span><span class="sxs-lookup"><span data-stu-id="68490-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="68490-129">Müssen Sie keine nachfolgenden Leerstellen nach dem unäroperator</span><span class="sxs-lookup"><span data-stu-id="68490-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="68490-130">Die binäre arithmetischen Operator-Richtlinie ist besonders wichtig.</span><span class="sxs-lookup"><span data-stu-id="68490-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="68490-131">Fehler beim Umschließen eines binäres `-` -Operator, in Kombination mit bestimmten Formatierungsoptionen zur Verfügung gestellt, zu interpretieren sie als ein unäres führen `-`.</span><span class="sxs-lookup"><span data-stu-id="68490-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="68490-132">Setzen Sie eine Definition benutzerdefinierter Operator mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="68490-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="68490-133">Verwenden Sie immer Leerzeichen, um eine Operatordefinition umschließen:</span><span class="sxs-lookup"><span data-stu-id="68490-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="68490-134">Für jeden benutzerdefinierten Operator an, die mit beginnt `*` und, die mehr als ein Zeichen ist, müssen Sie ein Leerzeichen am Anfang der Definition, die ein Compiler Mehrdeutigkeiten zu vermeiden, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="68490-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="68490-135">Aus diesem Grund empfehlen wir, dass Sie einfach die Definitionen aller Operatoren mit einem einzelnen Leerzeichen umschließen.</span><span class="sxs-lookup"><span data-stu-id="68490-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="68490-136">Setzen Sie die Funktion Parameter Pfeile mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="68490-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="68490-137">Wenn die Signatur einer Funktion zu definieren, verwenden Sie Leerraum um den `->` Symbol:</span><span class="sxs-lookup"><span data-stu-id="68490-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="68490-138">Setzen Sie die Argumente der Funktion mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="68490-138">Surround function arguments with white space</span></span>

<span data-ttu-id="68490-139">Wenn Sie eine Funktion zu definieren, verwenden Sie Leerraum um jedes Argument.</span><span class="sxs-lookup"><span data-stu-id="68490-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="type-annotations"></a><span data-ttu-id="68490-140">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="68490-140">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="68490-141">Argument-typanmerkungen rechts aufgefüllt-Funktion</span><span class="sxs-lookup"><span data-stu-id="68490-141">Right-pad function argument type annotations</span></span>

<span data-ttu-id="68490-142">Wenn Sie Argumente mit typanmerkungen zu definieren, verwenden Sie Leerzeichen nach den `:` Symbol:</span><span class="sxs-lookup"><span data-stu-id="68490-142">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="68490-143">Umschließen Rückgabetyp Anmerkungen mit einem Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="68490-143">Surround return type annotations with white space</span></span>

<span data-ttu-id="68490-144">Verwenden Sie in einer Let gebundenen Funktion oder einen Wert typanmerkung (Rückgabetyp bei einer Funktion), Leerzeichen vor und nach der `:` Symbol:</span><span class="sxs-lookup"><span data-stu-id="68490-144">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="68490-145">Formatieren von Leerzeilen</span><span class="sxs-lookup"><span data-stu-id="68490-145">Formatting blank lines</span></span>

* <span data-ttu-id="68490-146">Separate auf oberster Ebene-Funktion und der Klassendefinition mit zwei Leerzeilen.</span><span class="sxs-lookup"><span data-stu-id="68490-146">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="68490-147">Methodendefinitionen, die innerhalb einer Klasse werden durch eine einzelne leere Zeile getrennt.</span><span class="sxs-lookup"><span data-stu-id="68490-147">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="68490-148">Zusätzliche Leerzeilen einfügen können (selten) verwendet werden, um Gruppen von verwandten Funktionen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="68490-148">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="68490-149">Leere Zeilen können zwischen einer Reihe von verwandten Einzeiler (z. B. ein Satz von platzhalterimplementierungen) weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="68490-149">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="68490-150">Verwenden Sie Leerzeilen sparsam und nur dann in Funktionen, um logische Abschnitte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="68490-150">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="68490-151">Formatieren von Kommentaren</span><span class="sxs-lookup"><span data-stu-id="68490-151">Formatting comments</span></span>

<span data-ttu-id="68490-152">Ziehen Sie in der Regel mehrere Kommentaren mit doppelten Schrägstrichen blockskommentaren ML-Format vor.</span><span class="sxs-lookup"><span data-stu-id="68490-152">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="68490-153">Inlinekommentare sollte der erste Buchstabe groß geschrieben.</span><span class="sxs-lookup"><span data-stu-id="68490-153">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="68490-154">Namenskonventionen </span><span class="sxs-lookup"><span data-stu-id="68490-154">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="68490-155">Verwenden Sie CamelCase für die Klasse, ausdrucksgebundenen als auch Muster – gebunden Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="68490-155">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="68490-156">Es ist häufig und akzeptierte F# Stil, CamelCase für alle Namen als lokale Variablen oder in musterübereinstimmungen gebunden und Funktion Definitionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-156">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="68490-157">Lokale gebundene Funktionen in Klassen sollten auch CamelCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-157">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="68490-158">Verwenden Sie CamelCase für Öffentliche Modul-Bound-Funktionen</span><span class="sxs-lookup"><span data-stu-id="68490-158">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="68490-159">Wenn eine Modul-Bound-Funktion eine öffentliche API gehört, sollten sie CamelCase verwenden:</span><span class="sxs-lookup"><span data-stu-id="68490-159">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="68490-160">Verwenden Sie CamelCase für interne und private Modul-Bound-Werte und Funktionen</span><span class="sxs-lookup"><span data-stu-id="68490-160">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="68490-161">Verwenden Sie CamelCase für private Modul-Bound-Werte, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="68490-161">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="68490-162">Ad-hoc-Funktionen in Skripts</span><span class="sxs-lookup"><span data-stu-id="68490-162">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="68490-163">Werte, aus denen die interne Implementierung der ein Modul oder Typ</span><span class="sxs-lookup"><span data-stu-id="68490-163">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="68490-164">Verwenden Sie CamelCase für Parameter</span><span class="sxs-lookup"><span data-stu-id="68490-164">Use camelCase for parameters</span></span>

<span data-ttu-id="68490-165">Alle Parameter sollten CamelCase gemäß den Konventionen zur Namensgebung von .NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-165">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="68490-166">Verwenden Sie PascalCase für Module.</span><span class="sxs-lookup"><span data-stu-id="68490-166">Use PascalCase for modules</span></span>

<span data-ttu-id="68490-167">Alle Module (der obersten Ebene, interne, private, geschachtelte) sollten PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-167">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="68490-168">Verwenden von PascalCase für Deklarationen von Typen, Member und Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="68490-168">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="68490-169">Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten alle mit PascalCase benannt werden.</span><span class="sxs-lookup"><span data-stu-id="68490-169">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="68490-170">Außerdem sollten die Elemente innerhalb der Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-170">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="68490-171">Verwendung von PascalCase für Konstrukte auf .NET systeminterne</span><span class="sxs-lookup"><span data-stu-id="68490-171">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="68490-172">Namespaces, Ausnahmen, Ereignisse und Projekt /`.dll` Namen sollten auch PascalCase verwenden.</span><span class="sxs-lookup"><span data-stu-id="68490-172">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="68490-173">Nicht nur macht dies Verbrauch von anderen .NET-Sprachen können Sie erwarten, dass Kunden, es ist auch mit .NET Benennungskonventionen, die Sie wahrscheinlich konfrontiert sind konsistent.</span><span class="sxs-lookup"><span data-stu-id="68490-173">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="68490-174">Vermeiden Sie die Unterstriche im Namen</span><span class="sxs-lookup"><span data-stu-id="68490-174">Avoid underscores in names</span></span>

<span data-ttu-id="68490-175">In der Vergangenheit einige F# Bibliotheken Unterstriche im Namen verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68490-175">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="68490-176">Allerdings wird dies häufig nicht mehr akzeptiert, teilweise daran, dass sie mit .NET Benennungskonventionen verursacht einen Konflikt.</span><span class="sxs-lookup"><span data-stu-id="68490-176">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="68490-177">Dies bedeutet, dass einige F# Programmierer verwenden Unterstriche stark, teilweise historisch bedingt und Fehlertoleranz und Respekt ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="68490-177">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="68490-178">Bedenken Sie jedoch, dass der Stil häufig von anderen gefällt mir nicht ist, die eine Wahl darüber, ob sie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="68490-178">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="68490-179">Einige Ausnahmen umfasst die Interaktion mit nativen Komponenten, in denen Unterstriche sind sehr häufig.</span><span class="sxs-lookup"><span data-stu-id="68490-179">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="68490-180">Verwenden F# Operatoren</span><span class="sxs-lookup"><span data-stu-id="68490-180">Use standard F# operators</span></span>

<span data-ttu-id="68490-181">Die folgenden Operatoren werden definiert, der F# standard-Bibliothek und sollte verwendet werden, anstatt Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="68490-181">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="68490-182">Mit diesen Operatoren wird empfohlen, wie sie Code besser lesbar und idiomatische machen ist.</span><span class="sxs-lookup"><span data-stu-id="68490-182">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="68490-183">Entwickler mit einem Hintergrund mit OCaml oder andere funktionale Programmiersprache ggf. daran gewöhnt, Idiome zu sein.</span><span class="sxs-lookup"><span data-stu-id="68490-183">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="68490-184">Die folgende Liste enthält die empfohlenen F# Operatoren.</span><span class="sxs-lookup"><span data-stu-id="68490-184">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="68490-185">Verwenden Sie Generika Präfix-Syntax (`Foo<T>`) statt Postfix-Syntax (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="68490-185">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="68490-186">F#erbt sowohl den Postfix ML Stil für die Benennung von generischer Typen (z. B. `int list`) sowie das Präfix .NET Stil (z. B. `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="68490-186">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="68490-187">Bevorzugen Sie das .NET-Format, mit Ausnahme von vier bestimmte Typen:</span><span class="sxs-lookup"><span data-stu-id="68490-187">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="68490-188">Für F#-Listen, verwenden Sie die Postfix-Form: `int list` statt `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="68490-188">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="68490-189">Für F# ausprobiert haben, verwenden die Postfix-Form: `int option` statt `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="68490-189">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="68490-190">Für F# Arrays, verwenden Sie den syntaktischen Namen `int[]` statt `int array` oder `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="68490-190">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="68490-191">Verwenden Sie für Referenzzellen, `int ref` statt `ref<int>` oder `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="68490-191">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="68490-192">Verwenden Sie für alle anderen Dateitypen die Präfix-Form.</span><span class="sxs-lookup"><span data-stu-id="68490-192">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="68490-193">Formatieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="68490-193">Formatting tuples</span></span>

<span data-ttu-id="68490-194">Eine Instanziierung Tupel muss in Klammern ein, und die begrenzenden Kommas innerhalb von sollte z. B. durch ein Leerzeichen, gefolgt werden: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="68490-194">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="68490-195">Es wird häufig zum Auslassen von Klammern in Musterabgleich von Tupeln akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="68490-195">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="68490-196">Es wird häufig auch akzeptiert, Klammern weglassen, wenn das Tupel mit den Rückgabewert einer Funktion ist:</span><span class="sxs-lookup"><span data-stu-id="68490-196">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="68490-197">Zusammenfassend lässt sich sagen, lieber in Klammern gesetzte Tupel Instanziierungen, aber wenn Tupel für Musterabgleich oder einen Rückgabewert zu verwenden, gilt dies in Ordnung, Klammern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="68490-197">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="68490-198">Formatieren von Unterscheidungs-union-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="68490-198">Formatting discriminated union declarations</span></span>

<span data-ttu-id="68490-199">Einzug `|` in der Definition des Typs von 4 Leerzeichen:</span><span class="sxs-lookup"><span data-stu-id="68490-199">Indent `|` in type definition by 4 spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="68490-200">Formatieren von Unterscheidungs-unions</span><span class="sxs-lookup"><span data-stu-id="68490-200">Formatting discriminated unions</span></span>

<span data-ttu-id="68490-201">Instanziierte Unterscheidungs-Unions, die über mehrere Zeilen aufgeteilt sollte enthaltenen Daten einen neuen Bereich mit Einzug bieten:</span><span class="sxs-lookup"><span data-stu-id="68490-201">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="68490-202">Die schließende Klammer kann auch in einer neuen Zeile werden:</span><span class="sxs-lookup"><span data-stu-id="68490-202">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="68490-203">Formatieren von Datensatz-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="68490-203">Formatting record declarations</span></span>

<span data-ttu-id="68490-204">Einzug `{` Geben Sie in die Definition von 4 Leerzeichen und die Feldliste in der gleichen Zeile beginnen:</span><span class="sxs-lookup"><span data-stu-id="68490-204">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="68490-205">Das öffnendes-Token auf eine neue Zeile und dem schließenden-Token in einer neuen Zeile platziert ist vorzuziehen, wenn Sie für den Datensatz schnittstellenimplementierungen oder Member deklarieren:</span><span class="sxs-lookup"><span data-stu-id="68490-205">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="68490-206">Formatieren von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="68490-206">Formatting records</span></span>

<span data-ttu-id="68490-207">Kurze Datensätze können in einer Zeile geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="68490-207">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="68490-208">Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="68490-208">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="68490-209">Platzieren das öffnende token in einer neuen Zeile, mit dem Inhalt Registerkarten über einen Bereich, und das Schließen-Token in einer neuen Zeile ist vorzuziehen, wenn Sie sich befinden:</span><span class="sxs-lookup"><span data-stu-id="68490-209">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="68490-210">Einträge im Code mit anderen Einzug Bereichen verschieben</span><span class="sxs-lookup"><span data-stu-id="68490-210">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="68490-211">Übergeben sie in einer Funktion</span><span class="sxs-lookup"><span data-stu-id="68490-211">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="68490-212">Die gleichen Regeln gelten für Listen- und Elemente.</span><span class="sxs-lookup"><span data-stu-id="68490-212">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="68490-213">Formatieren von kopieren und Aktualisieren von Datensatz-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="68490-213">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="68490-214">Ein Datensatzausdruck von kopieren und aktualisieren ist immer noch einen Datensatz, damit ähnliche Richtlinien gelten.</span><span class="sxs-lookup"><span data-stu-id="68490-214">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="68490-215">Kurze Ausdrücke können in eine Zeile passen:</span><span class="sxs-lookup"><span data-stu-id="68490-215">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="68490-216">Längere Ausdrücke sollten neue Zeilen verwenden:</span><span class="sxs-lookup"><span data-stu-id="68490-216">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="68490-217">Und wie mit der Anleitung Datensatz möchten reservieren einzelne Zeilen für die geschweiften Klammern und einen Bereich auf der rechten Seite mit dem Ausdruck einziehen.</span><span class="sxs-lookup"><span data-stu-id="68490-217">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="68490-218">Beachten Sie, dass in einigen besonderen Fällen, z. B. einen Wert mit einem optionalen ohne Klammern umschließen Sie möglicherweise eine geschweifte Klammer in einer Zeile beibehalten müssen:</span><span class="sxs-lookup"><span data-stu-id="68490-218">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="68490-219">Formatieren von Listen und arrays</span><span class="sxs-lookup"><span data-stu-id="68490-219">Formatting lists and arrays</span></span>

<span data-ttu-id="68490-220">Schreiben von `x :: l` mit Leerzeichen vor und hinter der `::` Operator (`::` ist ein Infix-Operator, und daher von Leerzeichen eingeschlossen).</span><span class="sxs-lookup"><span data-stu-id="68490-220">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="68490-221">Listen- und Arrays, die in einer einzelnen Zeile deklariert werden. sollte ein Leerzeichen nach der öffnenden Klammer und vor der schließenden Klammer aufweisen:</span><span class="sxs-lookup"><span data-stu-id="68490-221">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="68490-222">Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifte Klammer-Like-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="68490-222">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="68490-223">Lassen Sie beispielsweise einem Leerzeichen zwischen einem `[` und `{`.</span><span class="sxs-lookup"><span data-stu-id="68490-223">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="68490-224">Das gleiche gilt für Listen oder Arrays von Tupeln.</span><span class="sxs-lookup"><span data-stu-id="68490-224">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="68490-225">Listen und Arrays, die über mehrere Zeilen aufgeteilt. Führen Sie eine ähnliche Regel, wie Datensätze:</span><span class="sxs-lookup"><span data-stu-id="68490-225">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="68490-226">Und wie mithilfe von Datensätzen, deklarieren die öffnenden und schließenden Klammern in einer eigenen Zeile Verschieben von Code um und Piping in Funktionen einfacher.</span><span class="sxs-lookup"><span data-stu-id="68490-226">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="68490-227">Formatierung-If-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68490-227">Formatting if expressions</span></span>

<span data-ttu-id="68490-228">Einzug von Bedingungen hängt von der Größe der Ausdrücke, die sie sich machen ab.</span><span class="sxs-lookup"><span data-stu-id="68490-228">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="68490-229">Wenn `cond`, `e1` und `e2` sind kurze, Schreiben Sie sie einfach auf eine Zeile:</span><span class="sxs-lookup"><span data-stu-id="68490-229">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="68490-230">Wenn entweder `cond`, `e1` oder `e2` sind länger, aber nicht mit mehreren Zeilen:</span><span class="sxs-lookup"><span data-stu-id="68490-230">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="68490-231">Wenn einer der Ausdrücke mit mehreren Zeilen sind:</span><span class="sxs-lookup"><span data-stu-id="68490-231">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="68490-232">Mehrere Bedingungen mit `elif` und `else` werden eingerückt unter dem gleichen Bereich wie die `if`:</span><span class="sxs-lookup"><span data-stu-id="68490-232">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="68490-233">Übereinstimmende Muster-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="68490-233">Pattern matching constructs</span></span>

<span data-ttu-id="68490-234">Verwenden einer `|` für jede Klausel einer Übereinstimmung mit ohne Einzug.</span><span class="sxs-lookup"><span data-stu-id="68490-234">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="68490-235">Wenn der Ausdruck kurz ist, können Sie erwägen, eine einzelne Zeile verwenden, wenn jede Teilausdruck auch einfach ist.</span><span class="sxs-lookup"><span data-stu-id="68490-235">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="68490-236">Wenn der Ausdruck auf der rechten Seite der Musterabgleich Pfeil zu groß ist, verschieben Sie sie auf der folgenden Zeile eingezogen einen Schritt aus dem `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="68490-236">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="68490-237">Mustervergleich von anonymen Funktionen, die gestartet wird, indem `function`, sollte im Allgemeinen nicht einrücken zu weit.</span><span class="sxs-lookup"><span data-stu-id="68490-237">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="68490-238">Beispielsweise reicht Einzug einen Bereich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="68490-238">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="68490-239">Mustervergleiche in Funktionen, die von definiert `let` oder `let rec` muss eingezogene 4 Leerzeichen nach dem Starten des `let`, auch wenn `function` -Schlüsselwort wird verwendet:</span><span class="sxs-lookup"><span data-stu-id="68490-239">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="68490-240">Wir empfehlen nicht, Pfeile ausrichten.</span><span class="sxs-lookup"><span data-stu-id="68490-240">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="68490-241">Formatierung Try / with-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="68490-241">Formatting try/with expressions</span></span>

<span data-ttu-id="68490-242">Musterabgleich für den Typ der Ausnahme sollte eingezogen werden, auf der gleichen Ebene wie `with`.</span><span class="sxs-lookup"><span data-stu-id="68490-242">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="68490-243">Formatieren von funktionsanwendung-parameter</span><span class="sxs-lookup"><span data-stu-id="68490-243">Formatting function parameter application</span></span>

<span data-ttu-id="68490-244">Die meisten funktionsanwendung-Parameter wird in der Regel in der gleichen Zeile durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="68490-244">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="68490-245">Wenn Sie, um Parameter an eine Funktion in einer neuen Zeile anzuwenden möchten, Rücken Sie diese durch einen Bereich.</span><span class="sxs-lookup"><span data-stu-id="68490-245">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="68490-246">Die gleichen Richtlinien gelten für Lambda-Ausdrücke als Argumente der Funktion.</span><span class="sxs-lookup"><span data-stu-id="68490-246">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="68490-247">Wenn der Text eines Lambda-Ausdrucks, der Text einer anderen Zeile eingerückt wird, indem Sie einen Bereich enthalten kann</span><span class="sxs-lookup"><span data-stu-id="68490-247">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="68490-248">Allerdings ist der Text eines Lambdaausdrucks mehrere Zeilen, sollten Sie ihn in eine separate Funktion Finanzierung anstelle einer mehrzeiligen-Konstrukt, das als einzelnes Argument an eine Funktion angewendet.</span><span class="sxs-lookup"><span data-stu-id="68490-248">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="68490-249">Formatieren von Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="68490-249">Formatting infix operators</span></span>

<span data-ttu-id="68490-250">Separate Operatoren durch Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="68490-250">Separate operators by spaces.</span></span> <span data-ttu-id="68490-251">Offensichtliche Ausnahmen von dieser Regel werden die `!` und `.` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="68490-251">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="68490-252">Infix-Ausdrücke sind in Ordnung LineUp auf dieselbe Spalte:</span><span class="sxs-lookup"><span data-stu-id="68490-252">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="68490-253">Formatieren von Pipeline-Operatoren</span><span class="sxs-lookup"><span data-stu-id="68490-253">Formatting pipeline operators</span></span>

<span data-ttu-id="68490-254">Pipeline `|>` Operatoren gesendet werden sollen, darunter die Ausdrücke, die sie verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="68490-254">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="68490-255">Formatieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="68490-255">Formatting modules</span></span>

<span data-ttu-id="68490-256">Code in einem lokalen Modul muss sich auf das Modul eingezogen werden, jedoch Code in einem Modul auf oberster Ebene sollten nicht eingerückt werden.</span><span class="sxs-lookup"><span data-stu-id="68490-256">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="68490-257">Namespace-Elemente müssen nicht mit Einzug dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="68490-257">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="68490-258">Formatieren von Object-Ausdrücke und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68490-258">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="68490-259">Object-Ausdrücke und Schnittstellen sollten auf die gleiche Weise mit ausgerichtet werden `member` nach 4 Leerzeichen eingerückt wird.</span><span class="sxs-lookup"><span data-stu-id="68490-259">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="68490-260">Formatieren von Leerzeichen in Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="68490-260">Formatting white space in expressions</span></span>

<span data-ttu-id="68490-261">Vermeiden Sie die überflüssigen Leerzeichen in F#-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="68490-261">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="68490-262">Benannte Argumente dürfen auch keine Leerzeichen, umgibt die `=`:</span><span class="sxs-lookup"><span data-stu-id="68490-262">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="68490-263">Formatierungsattribute</span><span class="sxs-lookup"><span data-stu-id="68490-263">Formatting attributes</span></span>

<span data-ttu-id="68490-264">[Attribute](../language-reference/attributes.md) werden über ein Konstrukt platziert:</span><span class="sxs-lookup"><span data-stu-id="68490-264">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="68490-265">Formatieren die Attribute für Parameter</span><span class="sxs-lookup"><span data-stu-id="68490-265">Formatting attributes on parameters</span></span>

<span data-ttu-id="68490-266">Attribute können auch Parameter stellen sein.</span><span class="sxs-lookup"><span data-stu-id="68490-266">Attributes can also be places on parameters.</span></span> <span data-ttu-id="68490-267">In diesem Fall platzieren Sie diese in der gleichen Zeile, die als Parameter und vor dem Namen:</span><span class="sxs-lookup"><span data-stu-id="68490-267">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="68490-268">Formatieren von mehreren Attributen</span><span class="sxs-lookup"><span data-stu-id="68490-268">Formatting multiple attributes</span></span>

<span data-ttu-id="68490-269">Wenn mehrere Attribute für ein Konstrukt, die nicht auf einen Parameter ist angewendet werden, sollten sie, dass es ein Attribut pro Zeile ist platziert werden:</span><span class="sxs-lookup"><span data-stu-id="68490-269">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="68490-270">Wenn für einen Parameter angewendet wird, sie muss in der gleichen Zeile und getrennt durch ein `;` Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="68490-270">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="68490-271">Formatieren von literalen</span><span class="sxs-lookup"><span data-stu-id="68490-271">Formatting literals</span></span>

<span data-ttu-id="68490-272">[F#Literale](../language-reference/literals.md) mithilfe der `Literal` Attribut sollte das Attribut in einer eigenen Zeile platzieren, und benennen CamelCase:</span><span class="sxs-lookup"><span data-stu-id="68490-272">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="68490-273">Verhindert, dass das Attribut auf derselben Zeile wie der Wert platziert.</span><span class="sxs-lookup"><span data-stu-id="68490-273">Avoid placing the attribute on the same line as the value.</span></span>
