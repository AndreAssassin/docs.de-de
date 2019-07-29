---
title: enum-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: e33877d2a5e79866bbef12cd9fec5cb11b044240
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433865"
---
# <a name="enum-c-reference"></a><span data-ttu-id="30952-102">enum (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="30952-102">enum (C# Reference)</span></span>

<span data-ttu-id="30952-103">Das Schlüsselwort `enum` wird zum Deklarieren einer Enumeration verwendet. Dies ist ein eigener Typ, der aus einer Gruppe benannter Konstanten besteht, die Enumeratorliste genannt wird.</span><span class="sxs-lookup"><span data-stu-id="30952-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>

<span data-ttu-id="30952-104">In der Regel ist es am besten, eine Enumeration direkt innerhalb eines Namespaces so zu definieren, dass alle Klassen im Namespace auf gleiche Weise darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="30952-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="30952-105">Eine Enumeration kann aber auch innerhalb einer Klasse oder einer Struktur geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="30952-105">However, an enum can also be nested within a class or struct.</span></span>

<span data-ttu-id="30952-106">Der erste Enumerator hat standardmäßig den Wert 0. Der Wert jedes nachfolgenden Enumerators wird um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="30952-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="30952-107">In der folgenden Enumeration gilt z. B.: `Sat` ist `0`, `Sun` ist `1`, `Mon` ist `2`usw.</span><span class="sxs-lookup"><span data-stu-id="30952-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="30952-108">Enumeratoren können mithilfe von Initialisierern die Standardwerte überschreiben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="30952-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="30952-109">In dieser Enumeration wird erzwungen, dass die Abfolge von Elementen mit `1` und nicht mit `0`beginnt.</span><span class="sxs-lookup"><span data-stu-id="30952-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="30952-110">Allerdings wird das Einfügen einer Konstanten mit dem Wert 0 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="30952-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="30952-111">Weitere Informationen finden Sie unter [Enumerationstypen](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="30952-111">For more information, see [Enumeration Types](../../programming-guide/enumeration-types.md).</span></span>

<span data-ttu-id="30952-112">Jeder Enumerationstyp hat einen zugrunde liegenden Typ, bei dem es sich um jeden [integralen numerischen Typ](../builtin-types/integral-numeric-types.md) handeln kann.</span><span class="sxs-lookup"><span data-stu-id="30952-112">Every enumeration type has an underlying type, which can be any [integral numeric type](../builtin-types/integral-numeric-types.md).</span></span> <span data-ttu-id="30952-113">Eine Ausnahme bildet [char](char.md).</span><span class="sxs-lookup"><span data-stu-id="30952-113">The [char](char.md) type cannot be an underlying type of an enum.</span></span> <span data-ttu-id="30952-114">Der zugrunde liegende Standardtyp von Enumerationselementen ist [int](../builtin-types/integral-numeric-types.md). Um eine Enumeration eines anderen ganzzahligen Typs, z. B. [byte](../builtin-types/integral-numeric-types.md)zu deklarieren, setzen Sie einen Doppelpunkt hinter dem Bezeichner, auf den der Typ folgt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="30952-114">The default underlying type of enumeration elements is [int](../builtin-types/integral-numeric-types.md). To declare an enum of another integral type, such as [byte](../builtin-types/integral-numeric-types.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="30952-115">Der Variablen eines Enumerationstyps kann jeder Wert im Bereich des zugrunde liegenden Typs zugewiesen werden. Die Werte sind nicht auf benannte Konstanten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="30952-115">A variable of an enumeration type can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>

<span data-ttu-id="30952-116">Der Standardwert von `enum E` ist der Wert, der vom Ausdruck `(E)0`erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="30952-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>

> [!NOTE]
> <span data-ttu-id="30952-117">Namen von Enumeratoren dürfen keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="30952-117">An enumerator cannot contain white space in its name.</span></span>

<span data-ttu-id="30952-118">Der zugrunde liegende Typ gibt an, wie viel Speicher für jeden Enumerator reserviert wird.</span><span class="sxs-lookup"><span data-stu-id="30952-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="30952-119">Eine explizite Typumwandlung ist jedoch erforderlich, um einen `enum` -Typ in einen ganzzahligen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="30952-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="30952-120">Durch die folgende Anweisung wird der `Sun` -Enumerator beispielsweise einer Variablen des Typs [int](../builtin-types/integral-numeric-types.md) zugewiesen. Dabei erfolgt für die Konvertierung von `enum` in `int`eine Typumwandlung.</span><span class="sxs-lookup"><span data-stu-id="30952-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../builtin-types/integral-numeric-types.md) by using a cast to convert from `enum` to `int`.</span></span>

```csharp
int x = (int)Day.Sun;
```

<span data-ttu-id="30952-121">Wenn <xref:System.FlagsAttribute?displayProperty=nameWithType> auf eine Enumeration mit Elementen angewendet wird, die mit einer bitweisen `OR` -Operation kombiniert werden können, beeinflusst das Attribut das Verhalten von `enum` bei der Verwendung bestimmter Tools.</span><span class="sxs-lookup"><span data-stu-id="30952-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="30952-122">Solche Änderungen sind bei Verwendung von Tools wie den Methoden der <xref:System.Console> -Klasse und der Ausdrucksauswertung zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="30952-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="30952-123">(Siehe das dritte Beispiel.)</span><span class="sxs-lookup"><span data-stu-id="30952-123">(See the third example.)</span></span>

## <a name="robust-programming"></a><span data-ttu-id="30952-124">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="30952-124">Robust programming</span></span>

<span data-ttu-id="30952-125">Wie bei Konstanten werden zur Kompilierzeit alle Verweise auf die einzelnen Werte einer Enumeration in numerische Literale konvertiert.</span><span class="sxs-lookup"><span data-stu-id="30952-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="30952-126">Dies kann, wie unter [Konstanten](../../programming-guide/classes-and-structs/constants.md) beschrieben, zu möglichen Versionsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="30952-126">This can create potential versioning issues as described in [Constants](../../programming-guide/classes-and-structs/constants.md).</span></span>

<span data-ttu-id="30952-127">Das Zuweisen zusätzlicher Werte zu neuen Enumerationsversionen oder das Ändern der Werte von Enumerationsmembern in einer neuen Version kann für abhängigen Quellcode Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="30952-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="30952-128">Enumerationswerte werden oft in [switch](switch.md) -Anweisungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="30952-128">Enum values often are used in [switch](switch.md) statements.</span></span> <span data-ttu-id="30952-129">Wenn dem `enum` -Typ weitere Elemente hinzugefügt wurden, kann der Standardabschnitt der „switch“-Anweisung unerwartet ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="30952-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>

<span data-ttu-id="30952-130">Falls andere Entwickler Ihren Code verwenden, sollten Sie Richtlinien festlegen, die angeben, wie deren Code reagieren soll, wenn `enum` -Typen neue Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="30952-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>

## <a name="example"></a><span data-ttu-id="30952-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30952-131">Example</span></span>

<span data-ttu-id="30952-132">Im folgenden Beispiel wird die Enumeration `Day`deklariert.</span><span class="sxs-lookup"><span data-stu-id="30952-132">In the following example, an enumeration, `Day`, is declared.</span></span> <span data-ttu-id="30952-133">Zwei Enumeratoren werden explizit in ganze Zahlen konvertiert und „Integer“-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="30952-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a><span data-ttu-id="30952-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30952-134">Example</span></span>

<span data-ttu-id="30952-135">Im folgenden Beispiel wird die Basistypoption verwendet, um ein `enum` zu deklarieren, dessen Member den Typ `long`haben.</span><span class="sxs-lookup"><span data-stu-id="30952-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="30952-136">Beachten Sie, dass obwohl der Enumeration der Typ `long`zugrunde liegt, die Enumerationsmember noch explizit mithilfe einer Typumwandlung in den Typ `long` umgewandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="30952-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a><span data-ttu-id="30952-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30952-137">Example</span></span>

<span data-ttu-id="30952-138">Im folgenden Codebeispiel werden die Verwendung des <xref:System.FlagsAttribute?displayProperty=nameWithType> -Attributs in einer `enum` -Deklaration und seine Wirkung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="30952-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a><span data-ttu-id="30952-139">Kommentare</span><span class="sxs-lookup"><span data-stu-id="30952-139">Comments</span></span>

<span data-ttu-id="30952-140">Wenn Sie `Flags`entfernen, werden im Beispiel die folgenden Werte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="30952-140">If you remove `Flags`, the example displays the following values:</span></span>

`5`

`5`

## <a name="c-language-specification"></a><span data-ttu-id="30952-141">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="30952-141">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="30952-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30952-142">See also</span></span>

- [<span data-ttu-id="30952-143">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="30952-143">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="30952-144">Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="30952-144">Enumeration Types</span></span>](../../programming-guide/enumeration-types.md)
- [<span data-ttu-id="30952-145">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="30952-145">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="30952-146">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="30952-146">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="30952-147">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="30952-147">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="30952-148">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="30952-148">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="30952-149">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="30952-149">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="30952-150">Benennungskonventionen für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="30952-150">Enum Naming Conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
