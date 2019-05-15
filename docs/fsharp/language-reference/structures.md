---
title: Strukturen
description: Erfahren Sie mehr über die F# Struktur, einen kompakter Objekttyp, der häufig effizienter als eine Klasse für Typen mit einer geringeren Menge an Daten und ein einfaches Verhalten.
ms.date: 05/16/2016
ms.openlocfilehash: dc302b975604bebcd145a385fb59b21417547c5e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645333"
---
# <a name="structures"></a><span data-ttu-id="db0ac-103">Strukturen</span><span class="sxs-lookup"><span data-stu-id="db0ac-103">Structures</span></span>

<span data-ttu-id="db0ac-104">Ein *Struktur* ist ein kompakter Objekttyp, die effizienter als eine Klasse für Typen sein können, die eine geringe Datenmenge und ein einfaches Verhalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="db0ac-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db0ac-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="db0ac-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db0ac-106">Remarks</span></span>

<span data-ttu-id="db0ac-107">Strukturen sind *Werttypen*, Felder, d. h., der sie gespeichert sind, direkt auf dem Stapel oder, wenn sie als verwendet werden, oder geben Sie die Elemente des Arrays, Inline im übergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="db0ac-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="db0ac-108">Im Gegensatz zu Klassen und Datensätzen verfügen Strukturen über eine Übergabewertsemantik.</span><span class="sxs-lookup"><span data-stu-id="db0ac-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="db0ac-109">Dies bedeutet, dass sie hauptsächlich für kleine Datenaggregate sinnvoll sind, die häufig aufgerufen und kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="db0ac-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="db0ac-110">In der vorherigen Syntax werden zwei Formen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="db0ac-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="db0ac-111">Die erste ist nicht die einfache Syntax, aber sie wird trotzdem häufig verwendet, da Sie bei Verwendung der Schlüsselwörter `struct` und `end` das `StructAttribute`-Attribut auslassen können, das in der zweiten Form angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="db0ac-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="db0ac-112">Sie können `StructAttribute` zu `Struct` abkürzen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="db0ac-113">Die *-Definition-Elemente-und-Typmember* in der vorherigen Syntax stellt Memberdeklarationen und-Definitionen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="db0ac-114">Strukturen können über Konstruktoren sowie änderbare und unveränderliche Felder verfügen, und sie können Member und Schnittstellenimplementierungen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="db0ac-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="db0ac-115">Weitere Informationen finden Sie unter [Mitglieder](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="db0ac-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="db0ac-116">Strukturen können nicht an der Vererbung beteiligt sein, sie können keine `let`- oder `do`-Bindungen enthalten und können nicht rekursiv Felder des eigenen Typs enthalten (obwohl sie Verweiszellen enthalten können, die auf den eigenen Typ verweisen).</span><span class="sxs-lookup"><span data-stu-id="db0ac-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="db0ac-117">Da Strukturen keine `let`-Bindungen zulassen, müssen Sie Felder in Strukturen mit dem `val`-Schlüsselwort deklarieren.</span><span class="sxs-lookup"><span data-stu-id="db0ac-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="db0ac-118">Das `val`-Schlüsselwort definiert ein Feld und den Typ, es lässt jedoch keine Initialisierung zu.</span><span class="sxs-lookup"><span data-stu-id="db0ac-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="db0ac-119">In diesem Fall werden `val`-Deklarationen mit 0 oder null initialisiert.</span><span class="sxs-lookup"><span data-stu-id="db0ac-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="db0ac-120">Aus diesem Grund erfordern Strukturen, die über einen impliziten Konstruktor verfügen (d. h. Parameter, die direkt nach dem Strukturnamen in der Deklaration angegeben werden), dass `val`-Deklarationen mit dem `DefaultValue`-Attribut gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="db0ac-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="db0ac-121">Strukturen, die über einen definierten Konstruktor verfügen, unterstützen weiterhin die Initialisierung mit 0 (null).</span><span class="sxs-lookup"><span data-stu-id="db0ac-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="db0ac-122">Aus diesem Grund ist das `DefaultValue`-Attribut eine Deklaration, dass der Wert 0 (Null) für das Feld gültig ist.</span><span class="sxs-lookup"><span data-stu-id="db0ac-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="db0ac-123">Implizite Konstruktoren für Strukturen führen keine Aktionen aus, da `let`- und `do`-Bindungen für den Typ nicht zulässig sind, aber die übergebenen impliziten Konstruktorparameterwerte sind als private Felder verfügbar.</span><span class="sxs-lookup"><span data-stu-id="db0ac-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="db0ac-124">Explizite Konstruktoren können eine Initialisierung von Feldwerten beinhalten.</span><span class="sxs-lookup"><span data-stu-id="db0ac-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="db0ac-125">Wenn Sie eine Struktur mit einem expliziten Konstruktor haben, unterstützt sie weiterhin die Initialisierung mit 0 (Null); Sie verwenden jedoch nicht das `DefaultValue`-Attribut auf den `val`-Deklarationen, da es mit dem expliziten Konstruktor in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="db0ac-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="db0ac-126">Weitere Informationen zu `val` Deklarationen finden Sie unter [explizite Felder: Die `val` Schlüsselwort](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="db0ac-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="db0ac-127">Attribute und Zugriffsmodifizierer sind für Strukturen zulässig und folgen denselben Regeln wie jene für andere Typen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="db0ac-128">Weitere Informationen finden Sie unter [Attribute](attributes.md) und [Zugriffssteuerung](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="db0ac-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="db0ac-129">Die folgenden Codebeispiele veranschaulichen Strukturdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="db0ac-130">ByRefLike Strukturen</span><span class="sxs-lookup"><span data-stu-id="db0ac-130">ByRefLike structs</span></span>

<span data-ttu-id="db0ac-131">Sie können definieren, dass Sie eigene Strukturen, die folgen können `byref`-Semantik wie: finden Sie unter [Byrefs](byrefs.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="db0ac-132">Dies erfolgt mit der <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:</span><span class="sxs-lookup"><span data-stu-id="db0ac-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="db0ac-133">`IsByRefLike` impliziert nicht `Struct`.</span><span class="sxs-lookup"><span data-stu-id="db0ac-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="db0ac-134">Beide müssen für den Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="db0ac-134">Both must be present on the type.</span></span>

<span data-ttu-id="db0ac-135">Ein "`byref`-wie" "Struct" in F# ist ein Stack gebundene Wert.</span><span class="sxs-lookup"><span data-stu-id="db0ac-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="db0ac-136">Sie wird nie auf dem verwalteten Heap zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="db0ac-137">Ein `byref`-Struktur für Hochleistungs-Programmierung nützlich ist, wie sie mit leistungsfähiger Prüfungen zur Lebensdauer und nicht-Capture erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="db0ac-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="db0ac-138">Die Regeln sind:</span><span class="sxs-lookup"><span data-stu-id="db0ac-138">The rules are:</span></span>

* <span data-ttu-id="db0ac-139">Sie können verwendet werden Methodenrückgabe als Funktionsparameter, Methodenparameter, lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="db0ac-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="db0ac-140">Sie können nicht statisch sein oder Instanzmember einer Klasse oder einer normalen Struktur.</span><span class="sxs-lookup"><span data-stu-id="db0ac-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="db0ac-141">Sie können nicht anhand des Konstrukte Closure erfasst werden (`async` Methoden oder Lambdaausdrücke).</span><span class="sxs-lookup"><span data-stu-id="db0ac-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="db0ac-142">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db0ac-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="db0ac-143">Obwohl diese Regeln sehr stark Nutzung einzuschränken, werden diese zur Erfüllung der Zusage von High Performance computing, auf sichere Weise.</span><span class="sxs-lookup"><span data-stu-id="db0ac-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="db0ac-144">Schreibgeschützte Strukturen</span><span class="sxs-lookup"><span data-stu-id="db0ac-144">ReadOnly structs</span></span>

<span data-ttu-id="db0ac-145">Sie können mit einer Anmerkung versehen Strukturen mit dem <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="db0ac-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="db0ac-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db0ac-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="db0ac-147">`IsReadOnly` impliziert nicht `Struct`.</span><span class="sxs-lookup"><span data-stu-id="db0ac-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="db0ac-148">Sie müssen beide haben Hinzufügen einer `IsReadOnly` Struktur.</span><span class="sxs-lookup"><span data-stu-id="db0ac-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="db0ac-149">Verwendung dieses Attributs gibt Metadaten können von F# und C# kennen, die sie behandeln, als `inref<'T>` und `in ref`bzw.</span><span class="sxs-lookup"><span data-stu-id="db0ac-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="db0ac-150">Definieren eines änderbaren Werts innerhalb einer Struktur Readonly erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="db0ac-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="db0ac-151">Struktur-Datensätze und Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="db0ac-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="db0ac-152">Sie können darstellen [Datensätze](records.md) und [Unterscheidungs-Unions](discriminated-unions.md) als Strukturen mit dem `[<Struct>]` Attribut.</span><span class="sxs-lookup"><span data-stu-id="db0ac-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="db0ac-153">Finden Sie alle Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="db0ac-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="db0ac-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db0ac-154">See also</span></span>

- [<span data-ttu-id="db0ac-155">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="db0ac-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="db0ac-156">Klassen</span><span class="sxs-lookup"><span data-stu-id="db0ac-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="db0ac-157">Datensätze</span><span class="sxs-lookup"><span data-stu-id="db0ac-157">Records</span></span>](records.md)
- [<span data-ttu-id="db0ac-158">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="db0ac-158">Members</span></span>](members/index.md)
