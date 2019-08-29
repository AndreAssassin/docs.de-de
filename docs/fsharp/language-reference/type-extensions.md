---
title: Typerweiterungen
description: Erfahren Sie F# , wie Sie mit Typerweiterungen einem zuvor definierten Objekttyp neue Member hinzufügen können.
ms.date: 02/08/2019
ms.openlocfilehash: 5d31d87095d3381e66dc32da4b6d7bb746886406
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106844"
---
# <a name="type-extensions"></a><span data-ttu-id="5d304-103">Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-103">Type extensions</span></span>

<span data-ttu-id="5d304-104">Typerweiterungen (auch als _Erweiterungen_bezeichnet) sind eine Reihe von Funktionen, mit denen Sie einem zuvor definierten Objekttyp neue Member hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="5d304-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="5d304-105">Die drei Features sind:</span><span class="sxs-lookup"><span data-stu-id="5d304-105">The three features are:</span></span>

- <span data-ttu-id="5d304-106">Systeminterne Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="5d304-107">Optionale Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-107">Optional type extensions</span></span>
- <span data-ttu-id="5d304-108">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="5d304-108">Extension methods</span></span>

<span data-ttu-id="5d304-109">Jede kann in verschiedenen Szenarien verwendet werden und hat unterschiedliche Kompromisse.</span><span class="sxs-lookup"><span data-stu-id="5d304-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d304-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d304-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="5d304-111">Systeminterne Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-111">Intrinsic type extensions</span></span>

<span data-ttu-id="5d304-112">Eine intrinsische Typerweiterung ist eine Typerweiterung, die einen benutzerdefinierten Typ erweitert.</span><span class="sxs-lookup"><span data-stu-id="5d304-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="5d304-113">Systeminterne Typerweiterungen müssen in derselben Datei **und** im gleichen Namespace oder Modul wie der Typ, den Sie erweitern, definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="5d304-114">Jede andere Definition führt zu [optionalen Typerweiterungen](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="5d304-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="5d304-115">Systeminterne Typerweiterungen sind manchmal eine saubere Möglichkeit, um die Funktionalität von der Typdeklaration zu trennen.</span><span class="sxs-lookup"><span data-stu-id="5d304-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="5d304-116">Im folgenden Beispiel wird gezeigt, wie eine systeminterne Typerweiterung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="5d304-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="5d304-117">Die Verwendung einer Typerweiterung ermöglicht es Ihnen, die folgenden voneinander zu trennen:</span><span class="sxs-lookup"><span data-stu-id="5d304-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="5d304-118">Die Deklaration eines `Variant` Typs.</span><span class="sxs-lookup"><span data-stu-id="5d304-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="5d304-119">Funktionalität zum Drucken der `Variant` Klasse, abhängig von ihrer Form.</span><span class="sxs-lookup"><span data-stu-id="5d304-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="5d304-120">Eine Möglichkeit für den Zugriff auf die Druck Funktionalität mit Objekt `.`Stil Notation</span><span class="sxs-lookup"><span data-stu-id="5d304-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="5d304-121">Dies ist eine Alternative zum Definieren alles als Member in `Variant`.</span><span class="sxs-lookup"><span data-stu-id="5d304-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="5d304-122">Obwohl es sich nicht um einen naturgemäß besseren Ansatz handelt, kann es in einigen Situationen eine saubere Darstellung der Funktionalität sein.</span><span class="sxs-lookup"><span data-stu-id="5d304-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="5d304-123">Systeminterne Typerweiterungen werden als Member des Typs, den Sie erweitern, kompiliert und für den Typ angezeigt, wenn der Typ durch Reflektion untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="5d304-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="5d304-124">Optionale Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-124">Optional type extensions</span></span>

<span data-ttu-id="5d304-125">Eine optionale Typerweiterung ist eine Erweiterung, die außerhalb des ursprünglichen Moduls, Namespace oder der Assembly des erweiterten Typs angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5d304-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="5d304-126">Optionale Typerweiterungen sind nützlich zum Erweitern eines Typs, den Sie nicht selbst definiert haben.</span><span class="sxs-lookup"><span data-stu-id="5d304-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="5d304-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d304-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="5d304-128">Sie können jetzt so `RepeatElements` aufrufen, als ob es ein Member <xref:System.Collections.Generic.IEnumerable%601> von ist, solange `Extensions` das Modul in dem Bereich geöffnet ist, in dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5d304-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="5d304-129">Optionale Erweiterungen werden nicht für den erweiterten Typ angezeigt, wenn Sie durch Reflektion untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="5d304-130">Optionale Erweiterungen müssen sich in Modulen befinden und befinden sich nur im Gültigkeitsbereich, wenn das Modul, das die Erweiterung enthält, geöffnet ist oder sich andernfalls im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="5d304-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="5d304-131">Member optionaler Erweiterungen werden in statische Member kompiliert, für die die Objektinstanz implizit als erster Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5d304-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="5d304-132">Sie agieren jedoch so, als ob Sie Instanzmember oder statische Member sind, je nachdem, wie Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="5d304-133">Optionale Erweiterungs Mitglieder sind auch für C# -oder-VB-Consumer nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="5d304-133">Optional extension members are also not visible to C# or VB consumers.</span></span> <span data-ttu-id="5d304-134">Sie können nur in anderem F# Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="5d304-135">Generische Einschränkung von systeminternen und optionalen Typerweiterungen</span><span class="sxs-lookup"><span data-stu-id="5d304-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="5d304-136">Es ist möglich, eine Typerweiterung für einen generischen Typ zu deklarieren, bei dem die Typvariable eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="5d304-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="5d304-137">Die Anforderung ist, dass die Einschränkung der Erweiterungs Deklaration mit der Einschränkung des deklarierten Typs übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5d304-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="5d304-138">Auch wenn Einschränkungen zwischen einem deklarierten Typ und einer Typerweiterung abgeglichen werden, ist es möglich, dass eine Einschränkung durch den Text eines erweiterten Members abgeleitet wird, der eine andere Anforderung für den Typparameter als den deklarierten Typ auferlegt.</span><span class="sxs-lookup"><span data-stu-id="5d304-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="5d304-139">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d304-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="5d304-140">Es gibt keine Möglichkeit, diesen Code zu erhalten, um mit einer optionalen Typerweiterung zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="5d304-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="5d304-141">Der `Sum` Member hat eine andere Einschränkung für `'T` (`static member get_Zero` und `static member (+)`) als für die Typerweiterung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5d304-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="5d304-142">Wenn Sie die Typerweiterung so ändern, dass Sie `Sum` die gleiche Einschränkung wie hat, stimmt nicht `IEnumerable<'T>`mehr mit der definierten Einschränkung für überein.</span><span class="sxs-lookup"><span data-stu-id="5d304-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="5d304-143">Wenn `member this.Sum` Sie `member inline this.Sum` in ändern, wird ein Fehler ausgegeben, dass Typeinschränkungen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5d304-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="5d304-144">Was gewünscht ist, sind statische Methoden, die "float in Space" sind, und können so dargestellt werden, als ob Sie einen Typ erweitern.</span><span class="sxs-lookup"><span data-stu-id="5d304-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="5d304-145">An dieser Stelle werden Erweiterungs Methoden benötigt.</span><span class="sxs-lookup"><span data-stu-id="5d304-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="5d304-146">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="5d304-146">Extension methods</span></span>

<span data-ttu-id="5d304-147">Schließlich können Erweiterungsmethoden (manchmal als "Erweiterungsmember des C#-Stil" bezeichnet) in F# als statische Membermethode in einer Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="5d304-148">Erweiterungs Methoden sind hilfreich, wenn Sie Erweiterungen für einen generischen Typ definieren möchten, der die Typvariable einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5d304-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="5d304-149">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d304-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="5d304-150">Wenn Sie verwendet wird, wird dieser Code so angezeigt, `Sum` als ob für <xref:System.Collections.Generic.IEnumerable%601>definiert ist, `Extensions` solange geöffnet ist oder sich im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="5d304-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="5d304-151">Weitere Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d304-151">Other remarks</span></span>

<span data-ttu-id="5d304-152">Typerweiterungen verfügen auch über die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="5d304-152">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="5d304-153">Alle Typen, auf die zugegriffen werden kann, können erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-153">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="5d304-154">Systeminterne und optionale Typerweiterungen können _einen beliebigen_ Elementtyp definieren, nicht nur Methoden.</span><span class="sxs-lookup"><span data-stu-id="5d304-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="5d304-155">Erweiterungs Eigenschaften sind z. b. ebenfalls möglich.</span><span class="sxs-lookup"><span data-stu-id="5d304-155">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="5d304-156">Das `self-identifier` Token in der [Syntax](type-extensions.md#syntax) stellt die Instanz des aufgerufenen Typs dar, genau wie normale Member.</span><span class="sxs-lookup"><span data-stu-id="5d304-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="5d304-157">Erweiterte Member können statische Member oder Instanzmember sein.</span><span class="sxs-lookup"><span data-stu-id="5d304-157">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="5d304-158">Typvariablen für eine Typerweiterung müssen mit den Einschränkungen des deklarierten Typs identisch sein.</span><span class="sxs-lookup"><span data-stu-id="5d304-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="5d304-159">Für Typerweiterungen gibt es auch die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="5d304-159">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="5d304-160">Typerweiterungen unterstützen keine virtuellen oder abstrakten Methoden.</span><span class="sxs-lookup"><span data-stu-id="5d304-160">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="5d304-161">Typerweiterungen unterstützen keine Überschreibungs Methoden als Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="5d304-161">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="5d304-162">Typerweiterungen unterstützen keine [statisch aufgelösten Typparameter](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5d304-162">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="5d304-163">Optionale Typerweiterungen unterstützen keine Konstruktoren als Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="5d304-163">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="5d304-164">Typerweiterungen können nicht für [typabkürzungen](type-abbreviations.md)definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5d304-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="5d304-165">Typerweiterungen sind für `byref<'T>` ungültig (obwohl Sie deklariert werden können).</span><span class="sxs-lookup"><span data-stu-id="5d304-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="5d304-166">Typerweiterungen sind für Attribute ungültig (Sie können jedoch als deklariert werden).</span><span class="sxs-lookup"><span data-stu-id="5d304-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="5d304-167">Sie können definieren, Erweiterungen, die andere Methoden, mit dem gleichen Namen zu überladen, aber F#-Compiler bevorzugt nicht-Erweiterungsmethoden gibt es ist ein Mehrdeutiger Aufruf.</span><span class="sxs-lookup"><span data-stu-id="5d304-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="5d304-168">Wenn zum Schluss mehrere systeminterne Typerweiterungen für einen Typ vorhanden sind, müssen alle Elemente eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="5d304-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="5d304-169">Bei optionalen Typerweiterungen können Member in unterschiedlichen Typerweiterungen, die auf den gleichen Typ erweitert werden, die gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5d304-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="5d304-170">Mehrdeutigkeitsfehler treten nur auf, wenn Clientcode zwei unterschiedliche Gültigkeitsbereiche öffnet, die die gleichen Membernamen definieren.</span><span class="sxs-lookup"><span data-stu-id="5d304-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d304-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d304-171">See also</span></span>

- [<span data-ttu-id="5d304-172">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="5d304-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5d304-173">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="5d304-173">Members</span></span>](./members/index.md)
