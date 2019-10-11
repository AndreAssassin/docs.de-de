---
title: Einschränkungen
description: Erfahren Sie F# mehr über Einschränkungen für generische Typparameter, um die Anforderungen für ein Typargument in einem generischen Typ oder einer generischen Funktion anzugeben.
ms.date: 05/16/2016
ms.openlocfilehash: 9912ba63138d893a7c616661dd2b1cbdbe51916c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736793"
---
# <a name="constraints"></a><span data-ttu-id="12552-103">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="12552-103">Constraints</span></span>

<span data-ttu-id="12552-104">In diesem Thema werden Einschränkungen beschrieben, die Sie auf generische Typparameter anwenden können, um die Anforderungen für ein Typargument in einem generischen Typ oder einer generischen Funktion anzugeben</span><span class="sxs-lookup"><span data-stu-id="12552-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="12552-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="12552-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="12552-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12552-106">Remarks</span></span>

<span data-ttu-id="12552-107">Es gibt mehrere unterschiedliche Einschränkungen, die Sie anwenden können, um die Typen einzuschränken, die in einem generischen Typ verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="12552-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="12552-108">In der folgenden Tabelle sind diese Einschränkungen aufgeführt und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12552-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="12552-109">Constraint</span><span class="sxs-lookup"><span data-stu-id="12552-109">Constraint</span></span>|<span data-ttu-id="12552-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="12552-110">Syntax</span></span>|<span data-ttu-id="12552-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12552-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="12552-112">Typeinschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-112">Type Constraint</span></span>|<span data-ttu-id="12552-113">*Type-Parameter* : &gt;- *Typ*</span><span class="sxs-lookup"><span data-stu-id="12552-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="12552-114">Der angegebene Typ muss mit dem angegebenen Typ übereinstimmen oder davon abgeleitet werden, oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ die-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="12552-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="12552-115">NULL-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-115">Null Constraint</span></span>|<span data-ttu-id="12552-116">*Type-Parameter* : NULL</span><span class="sxs-lookup"><span data-stu-id="12552-116">*type-parameter* : null</span></span>|<span data-ttu-id="12552-117">Der angegebene Typ muss das NULL-Literalzeichen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="12552-117">The provided type must support the null literal.</span></span> <span data-ttu-id="12552-118">Dies schließt alle .NET-Objekttypen ein F# , jedoch keine Listen-, Tupel-, Funktions-, Klassen-, Datensatz-oder Union-Typen.</span><span class="sxs-lookup"><span data-stu-id="12552-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="12552-119">Explizite Member-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-119">Explicit Member Constraint</span></span>|<span data-ttu-id="12552-120">[(]*Typparameter* [oder... oder *Typparameter*)]: (*Membersignatur*)</span><span class="sxs-lookup"><span data-stu-id="12552-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="12552-121">Mindestens eines der bereitgestellten Typargumente muss über einen Member verfügen, der über die angegebene Signatur verfügt. nicht für die gemeinsame Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="12552-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="12552-122">Member müssen entweder explizit für den Typ oder einen Teil einer impliziten Typerweiterung definiert sein, damit Sie gültige Ziele für eine explizite Element Einschränkung sind.</span><span class="sxs-lookup"><span data-stu-id="12552-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="12552-123">Konstruktoreinschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-123">Constructor Constraint</span></span>|<span data-ttu-id="12552-124">*Type-Parameter* : (New: Unit-&gt; ' a)</span><span class="sxs-lookup"><span data-stu-id="12552-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="12552-125">Der angegebene Typ muss über einen Parameter losen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="12552-125">The provided type must have a parameterless constructor.</span></span>|
|<span data-ttu-id="12552-126">Werttyp Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-126">Value Type Constraint</span></span>|<span data-ttu-id="12552-127">:-Struktur</span><span class="sxs-lookup"><span data-stu-id="12552-127">: struct</span></span>|<span data-ttu-id="12552-128">Der angegebene Typ muss ein .net-Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="12552-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="12552-129">Verweistyp Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-129">Reference Type Constraint</span></span>|<span data-ttu-id="12552-130">: Not-Struktur</span><span class="sxs-lookup"><span data-stu-id="12552-130">: not struct</span></span>|<span data-ttu-id="12552-131">Der angegebene Typ muss ein .net-Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="12552-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="12552-132">Enumerationstyp Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="12552-133">: "no__t" vom Typ "-0",*zugrunde liegender Typ*&gt;</span><span class="sxs-lookup"><span data-stu-id="12552-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="12552-134">Der angegebene Typ muss ein enumerierter Typ sein, der den angegebenen zugrunde liegenden Typ aufweist. nicht für die gemeinsame Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="12552-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="12552-135">Delegateinschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-135">Delegate Constraint</span></span>|<span data-ttu-id="12552-136">: Delegat @ no__t-0*Tuple-Parameter-Type*, *Rückgabetyp*&gt;</span><span class="sxs-lookup"><span data-stu-id="12552-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="12552-137">Der angegebene Typ muss ein Delegattyp sein, der über die angegebenen Argumente und den Rückgabewert verfügt. nicht für die gemeinsame Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="12552-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="12552-138">Vergleichs Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-138">Comparison Constraint</span></span>|<span data-ttu-id="12552-139">: Vergleich</span><span class="sxs-lookup"><span data-stu-id="12552-139">: comparison</span></span>|<span data-ttu-id="12552-140">Der angegebene Typ muss einen Vergleich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="12552-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="12552-141">Gleichheits Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-141">Equality Constraint</span></span>|<span data-ttu-id="12552-142">: Gleichheit</span><span class="sxs-lookup"><span data-stu-id="12552-142">: equality</span></span>|<span data-ttu-id="12552-143">Der angegebene Typ muss Gleichheit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="12552-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="12552-144">Nicht verwaltete Einschränkung</span><span class="sxs-lookup"><span data-stu-id="12552-144">Unmanaged Constraint</span></span>|<span data-ttu-id="12552-145">: nicht verwaltet</span><span class="sxs-lookup"><span data-stu-id="12552-145">: unmanaged</span></span>|<span data-ttu-id="12552-146">Der angegebene Typ muss ein nicht verwalteter Typ sein.</span><span class="sxs-lookup"><span data-stu-id="12552-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="12552-147">Nicht verwaltete Typen sind entweder bestimmte primitive Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, 0, 1, 2 oder 3), Enumerationstypen, 4 oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen sind.</span><span class="sxs-lookup"><span data-stu-id="12552-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="12552-148">Sie müssen eine Einschränkung hinzufügen, wenn Ihr Code eine Funktion verwenden muss, die für den Einschränkungstyp verfügbar ist, aber nicht für allgemeine Typen.</span><span class="sxs-lookup"><span data-stu-id="12552-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="12552-149">Wenn Sie z. b. die Typeinschränkung verwenden, um einen Klassentyp anzugeben, können Sie eine beliebige Methode dieser Klasse in der generischen Funktion oder dem generischen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="12552-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="12552-150">Das Angeben von Einschränkungen ist manchmal beim expliziten Schreiben von Typparametern erforderlich, da der Compiler ohne Einschränkung nicht überprüfen kann, ob die von Ihnen verwendeten Funktionen für jeden Typ verfügbar sind, der zur Laufzeit für den Typ bereitgestellt wird. Parame.</span><span class="sxs-lookup"><span data-stu-id="12552-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="12552-151">Die gängigsten Einschränkungen, die Sie F# im Code verwenden, sind Typeinschränkungen, die Basisklassen oder Schnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="12552-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="12552-152">Die anderen Einschränkungen werden entweder von der F#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, die zum Implementieren von arithmetischen Operatoren überladen verwendet oder dienen hauptsächlich deshalb, weil F# die vollständige unterstützt Reihe von Einschränkungen, die von der common Language Runtime unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="12552-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="12552-153">Beim Typrückschluss werden einige Einschränkungen automatisch vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="12552-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="12552-154">Wenn Sie z. b. den `+`-Operator in einer Funktion verwenden, leitet der Compiler eine explizite Element Einschränkung für Variablen Typen ab, die im Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12552-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="12552-155">Der folgende Code veranschaulicht einige Einschränkungs Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="12552-155">The following code illustrates some constraint declarations:</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="12552-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12552-156">See also</span></span>

- [<span data-ttu-id="12552-157">Generics</span><span class="sxs-lookup"><span data-stu-id="12552-157">Generics</span></span>](index.md)
- [<span data-ttu-id="12552-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="12552-158">Constraints</span></span>](constraints.md)
