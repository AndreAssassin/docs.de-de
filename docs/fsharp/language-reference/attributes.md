---
title: Attribute
description: Erfahren Sie F# , wie Attribute das Anwenden von Metadaten auf ein Programmierkonstrukt ermöglichen.
ms.date: 05/16/2016
ms.openlocfilehash: c9691a13ff1e9e892e93a967136a99849da25f1f
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567501"
---
# <a name="attributes"></a><span data-ttu-id="3e2d8-103">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e2d8-103">Attributes</span></span>

<span data-ttu-id="3e2d8-104">Attribute ermöglichen das Anwenden von Metadaten auf ein Programmierkonstrukt.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e2d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e2d8-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="3e2d8-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e2d8-106">Remarks</span></span>

<span data-ttu-id="3e2d8-107">In der vorherigen Syntax ist das *Ziel* optional und gibt, sofern vorhanden, die Art der Programm Entität an, für die das Attribut gilt.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="3e2d8-108">Gültige Werte für das *Ziel* werden in der Tabelle angezeigt, die später in diesem Dokument angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="3e2d8-109">Der *Attribut Name* verweist auf den Namen (möglicherweise mit Namespaces qualifiziert) eines gültigen Attributtyps mit oder ohne das Suffix `Attribute` , das normalerweise in Attributtyp Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="3e2d8-110">Der Typ `ObsoleteAttribute` kann z. b. nur `Obsolete` in diesem Kontext verkürzt werden.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="3e2d8-111">Die *Argumente* sind die Argumente für den Konstruktor für den Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="3e2d8-112">Wenn ein Attribut über einen Standardkonstruktor verfügt, können die Argumentliste und die Klammern ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="3e2d8-113">Attribute unterstützen sowohl positionelle Argumente als auch benannte Argumente.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="3e2d8-114">*Positions Argumente* sind Argumente, die in der Reihenfolge verwendet werden, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="3e2d8-115">Benannte Argumente können verwendet werden, wenn das Attribut öffentliche Eigenschaften hat.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="3e2d8-116">Sie können diese mithilfe der folgenden Syntax in der Argumentliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="3e2d8-117">Solche Eigenschafts Initialisierungen können in beliebiger Reihenfolge vorliegen, aber Sie müssen beliebige Positions Argumente einhalten.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="3e2d8-118">Im folgenden finden Sie ein Beispiel für ein Attribut, das Positions Argumente und Eigenschafts Initialisierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="3e2d8-119">In diesem Beispiel ist `DllImportAttribute`das-Attribut, das in kürzerer Form verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="3e2d8-120">Das erste Argument ist ein Positions Parameter, und das zweite Argument ist eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="3e2d8-121">Attribute sind ein .net-Programmierkonstrukt, mit dem ein Objekt, das als *Attribut* bezeichnet wird, einem Typ oder einem anderen Programmelement zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="3e2d8-122">Das Programmelement, auf das ein Attribut angewendet wird, wird als *Attribut Ziel*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="3e2d8-123">Das Attribut enthält normalerweise Metadaten zum Ziel.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="3e2d8-124">In diesem Kontext können Metadaten beliebige Daten über den Typ sein, der nicht die Felder und Member ist.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="3e2d8-125">Attribute in F# können angewendet werden, um die folgenden Konstrukte der Programmierung: Funktionen, Methoden, Assemblys, Modulen, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie Parameter und Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="3e2d8-126">Attribute sind für Bindungen innerhalb `let` von Klassen, Ausdrücken oder Workflow Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="3e2d8-127">In der Regel wird die Attribut Deklaration direkt vor der Deklaration des Attribut Ziels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="3e2d8-128">Mehrere Attribut Deklarationen können wie folgt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="3e2d8-129">Sie können Attribute zur Laufzeit mithilfe der .NET-Reflektion Abfragen.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="3e2d8-130">Sie können mehrere Attribute einzeln deklarieren, wie im vorherigen Codebeispiel, oder Sie können Sie in einer Gruppe von Klammern deklarieren, wenn Sie die einzelnen Attribute und Konstruktoren mit einem Semikolon trennen, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="3e2d8-131">Zu den Attributen zählen in `Obsolete` der Regel das Attribut, Attribute für Sicherheitsüberlegungen, Attribute für COM-Unterstützung, Attribute, die sich auf den Besitz von Code beziehen, und Attribute, die angeben, ob ein Typ serialisiert werden kann</span><span class="sxs-lookup"><span data-stu-id="3e2d8-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="3e2d8-132">Im folgenden Beispiel wird die Verwendung des `Obsolete` -Attributs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="3e2d8-133">Für die Attribut Ziele `assembly` und `module`wenden Sie die Attribute auf eine Bindung der obersten Ebene `do` in der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="3e2d8-134">Sie können das Wort `assembly` oder `module` in die Attribut Deklaration wie folgt einschließen.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="3e2d8-135">Wenn Sie weglassen, dass das Attributziel für ein Attribut auf eine `do` Bindung, die F#-Compiler versucht, das Attributziel zu bestimmen, die sinnvoll für dieses Attribut ist.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="3e2d8-136">Viele Attribut Klassen verfügen über ein Attribut vom `System.AttributeUsageAttribute` Typ, das Informationen über die möglichen Ziele enthält, die für dieses Attribut unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="3e2d8-137">Wenn das `System.AttributeUsageAttribute` angibt, dass das Attribut Funktionen als Ziele unterstützt, wird das Attribut auf den Haupteinstiegspunkt des Programms angewendet.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="3e2d8-138">Wenn das `System.AttributeUsageAttribute` angibt, dass das Attribut Assemblys als Ziele unterstützt, übernimmt der Compiler das-Attribut, das auf die Assembly angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="3e2d8-139">Die meisten Attribute gelten nicht für Funktionen und Assemblys, aber in Fällen, in denen Sie dies tun, wird das Attribut für die Hauptfunktion des Programms übernommen.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="3e2d8-140">Wenn das Attribut Ziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="3e2d8-141">Obwohl Sie in der Regel das Attribut Ziel nicht explizit angeben müssen, sind in der folgenden Tabelle die gültigen Werte für *target* in einem Attribut sowie Beispiele für die Verwendung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e2d8-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="3e2d8-142">Attribut Ziel</span><span class="sxs-lookup"><span data-stu-id="3e2d8-142">Attribute target</span></span></td>
    <th><span data-ttu-id="3e2d8-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e2d8-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-144">Assembly</span><span class="sxs-lookup"><span data-stu-id="3e2d8-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-145">return</span><span class="sxs-lookup"><span data-stu-id="3e2d8-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-146">Feld</span><span class="sxs-lookup"><span data-stu-id="3e2d8-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-147">property</span><span class="sxs-lookup"><span data-stu-id="3e2d8-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="3e2d8-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="3e2d8-149">Typ</span><span class="sxs-lookup"><span data-stu-id="3e2d8-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(Sequential)&gt;] 
type MyStruct = 
struct 
x : byte
y : int
end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="3e2d8-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e2d8-150">See also</span></span>

- [<span data-ttu-id="3e2d8-151">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="3e2d8-151">F# Language Reference</span></span>](index.md)
