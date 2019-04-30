---
title: Indizierte Eigenschaften
description: Erfahren Sie mehr über indizierte Eigenschaften in F#, das arrayähnlichen Zugriff auf die sortierten Daten ermöglichen.
ms.date: 10/17/2018
ms.openlocfilehash: bc330641c451973ddefa0a34fe6e757a808f6cb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903824"
---
# <a name="indexed-properties"></a><span data-ttu-id="e875b-103">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e875b-103">Indexed Properties</span></span>

<span data-ttu-id="e875b-104">Beim Definieren einer Klasse, die für sortierte Daten abstrahiert, kann es manchmal hilfreich, indizierten Zugriff auf diese Daten bereitstellen, ohne die zugrunde liegende Implementierung verfügbar zu machen sein.</span><span class="sxs-lookup"><span data-stu-id="e875b-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="e875b-105">Dies erfolgt mit der `Index` Member.</span><span class="sxs-lookup"><span data-stu-id="e875b-105">This is done with the `Index` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="e875b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e875b-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="e875b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e875b-107">Remarks</span></span>

<span data-ttu-id="e875b-108">Die Formen der vorherigen Syntax zeigen, wie Sie indizierte Eigenschaften definiert, die sowohl eine `get` und ein `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur.</span><span class="sxs-lookup"><span data-stu-id="e875b-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="e875b-109">Sie können auch kombiniert sowohl die Syntax für nur Get- und die Syntax für die Gruppe nur und erzeugen eine Eigenschaft, die sowohl get- und Set hat.</span><span class="sxs-lookup"><span data-stu-id="e875b-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="e875b-110">Diese Form können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="e875b-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="e875b-111">Mit dem Namen `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e875b-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="e875b-112">Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie zugreifen können, mithilfe einer arrayähnlichen Syntax in der Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="e875b-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="e875b-113">Z. B. wenn `o` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `o.[index]` wird verwendet, um die Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e875b-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="e875b-114">Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft ist zum Bereitstellen des Namens der Eigenschaft und der Index in Klammern ein, wie ein reguläres Element.</span><span class="sxs-lookup"><span data-stu-id="e875b-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="e875b-115">Z. B. wenn die Eigenschaft `o` heißt `Ordinal`, Sie schreiben `o.Ordinal(index)` , darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e875b-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="e875b-116">Unabhängig davon, welche Form, die Sie verwenden, sollten Sie immer die Curry-Form für die Set-Methode für eine indizierte Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="e875b-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="e875b-117">Weitere Informationen zu Funktionen mit Currying, finden Sie unter [Funktionen](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="e875b-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="e875b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e875b-118">Example</span></span>

<span data-ttu-id="e875b-119">Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßigen indizierte Eigenschaften, die verfügen über get- und set-Methoden.</span><span class="sxs-lookup"><span data-stu-id="e875b-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="e875b-120">Output</span><span class="sxs-lookup"><span data-stu-id="e875b-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="e875b-121">Indizierte Eigenschaften mit mehreren Indexwerten</span><span class="sxs-lookup"><span data-stu-id="e875b-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="e875b-122">Indizierte Eigenschaften können mehr als ein Indexwert haben.</span><span class="sxs-lookup"><span data-stu-id="e875b-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="e875b-123">In diesem Fall werden die Werte durch Kommas getrennt, wenn die Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e875b-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="e875b-124">Die Set-Methode in eine entsprechende Eigenschaft benötigen zwei Curry-Argumente, das erste Argument ist ein Tupel, die die Schlüssel und dem zweiten ist, das den festzulegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="e875b-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="e875b-125">Der folgende Code veranschaulicht die Verwendung mit mehrere Indexwerte einer indizierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e875b-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="e875b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e875b-126">See also</span></span>

- [<span data-ttu-id="e875b-127">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="e875b-127">Members</span></span>](index.md)
