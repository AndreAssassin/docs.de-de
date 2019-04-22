---
title: long – C#-Referenz
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: 997ce7399dc9742076932b213811abd1f847e60b
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613290"
---
# <a name="long-c-reference"></a><span data-ttu-id="d51cf-102">long (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d51cf-102">long (C# Reference)</span></span>

<span data-ttu-id="d51cf-103">`long` kennzeichnet einen Ganzzahltyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d51cf-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="d51cf-104">Typ</span><span class="sxs-lookup"><span data-stu-id="d51cf-104">Type</span></span>|<span data-ttu-id="d51cf-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="d51cf-105">Range</span></span>|<span data-ttu-id="d51cf-106">Größe</span><span class="sxs-lookup"><span data-stu-id="d51cf-106">Size</span></span>|<span data-ttu-id="d51cf-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="d51cf-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`long`|<span data-ttu-id="d51cf-108">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="d51cf-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="d51cf-109">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d51cf-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="d51cf-110">Literale</span><span class="sxs-lookup"><span data-stu-id="d51cf-110">Literals</span></span>

<span data-ttu-id="d51cf-111">Sie können eine `long`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d51cf-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>

<span data-ttu-id="d51cf-112">Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `long`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d51cf-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]

> [!NOTE]
> <span data-ttu-id="d51cf-113">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="d51cf-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d51cf-114">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="d51cf-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d51cf-115">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d51cf-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>
- <span data-ttu-id="d51cf-116">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="d51cf-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="d51cf-117">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="d51cf-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="d51cf-118">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d51cf-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="d51cf-119">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d51cf-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

<span data-ttu-id="d51cf-120">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d51cf-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="d51cf-121">Das Suffix `L` kennzeichnet ein `long`.</span><span class="sxs-lookup"><span data-stu-id="d51cf-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="d51cf-122">Im folgenden Beispiel wird das `L`-Suffix verwendet, um eine lange ganze Zahl anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d51cf-122">The following example uses the `L` suffix to denote a long integer:</span></span>

```csharp
long value = 4294967296L;
```

> [!NOTE]
> <span data-ttu-id="d51cf-123">Sie können auch Kleinbuchstabe „l“ als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="d51cf-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="d51cf-124">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="d51cf-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="d51cf-125">Verwenden Sie aus Gründen der Klarheit „L“.</span><span class="sxs-lookup"><span data-stu-id="d51cf-125">Use "L" for clarity.</span></span>

<span data-ttu-id="d51cf-126">Wenn Sie das Suffix `L` verwenden, wird der Typ des Ganzzahlliterals entweder als `long` oder [ulong](../../../csharp/language-reference/keywords/ulong.md) bestimmt, abhängig von seiner Größe.</span><span class="sxs-lookup"><span data-stu-id="d51cf-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="d51cf-127">In diesem Fall ist er `long`, weil er kleiner als der Bereich von [ulong](../../../csharp/language-reference/keywords/ulong.md) ist.</span><span class="sxs-lookup"><span data-stu-id="d51cf-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>

<span data-ttu-id="d51cf-128">Das Suffix wird häufig zum Aufrufen überladener Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="d51cf-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="d51cf-129">Die folgenden überladenen Methoden z.B. verfügen über Parameter des Typs `long` und [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="d51cf-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(long l) {}
```

<span data-ttu-id="d51cf-130">Das `L`-Suffix gewährleistet, dass die richtige Überladung aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="d51cf-130">The `L` suffix guarantees that the correct overload is called:</span></span>

```csharp
SampleMethod(5);    // Calls the method with the int parameter
SampleMethod(5L);   // Calls the method with the long parameter
```

<span data-ttu-id="d51cf-131">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="d51cf-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="d51cf-132">int</span><span class="sxs-lookup"><span data-stu-id="d51cf-132">int</span></span>](int.md)
2. [<span data-ttu-id="d51cf-133">uint</span><span class="sxs-lookup"><span data-stu-id="d51cf-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="d51cf-134">ulong</span><span class="sxs-lookup"><span data-stu-id="d51cf-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)

<span data-ttu-id="d51cf-135">Das Literal 4294967296 im vorhergehenden Beispiel ist vom Typ `long`, da er den Bereich von [uint](../../../csharp/language-reference/keywords/uint.md) überschreitet (Speichergrößen von ganzzahligen Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="d51cf-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>

<span data-ttu-id="d51cf-136">Wenn Sie den `long`-Typ mit anderen ganzzahligen Typen im selben Ausdruck verwenden, wird der Ausdruck als `long` ausgewertet (oder [bool](../../../csharp/language-reference/keywords/bool.md) im Fall von relationalen oder booleschen Ausdrücken).</span><span class="sxs-lookup"><span data-stu-id="d51cf-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="d51cf-137">Der folgende Ausdruck wird z.B. als `long` ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="d51cf-137">For example, the following expression evaluates as `long`:</span></span>

```csharp
898L + 88
```

<span data-ttu-id="d51cf-138">Weitere Informationen zu arithmetischen Ausdrücken mit gemischten Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d51cf-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="d51cf-139">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d51cf-139">Conversions</span></span>

<span data-ttu-id="d51cf-140">Es gibt eine vordefinierte implizite Konvertierung von `long` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="d51cf-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="d51cf-141">Ansonsten muss eine Umwandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d51cf-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="d51cf-142">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="d51cf-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>

```csharp
int x = 8L;        // Error: no implicit conversion from long to int
int y = (int)8L;   // OK: explicit conversion to int
```

<span data-ttu-id="d51cf-143">Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `long`.</span><span class="sxs-lookup"><span data-stu-id="d51cf-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>

<span data-ttu-id="d51cf-144">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `long` gibt.</span><span class="sxs-lookup"><span data-stu-id="d51cf-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="d51cf-145">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d51cf-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
long x = 3.0;         // Error: no implicit conversion from double
long y = (long)3.0;   // OK: explicit conversion
```

## <a name="c-language-specification"></a><span data-ttu-id="d51cf-146">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d51cf-146">C# Language Specification</span></span>

<span data-ttu-id="d51cf-147">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d51cf-147">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d51cf-148">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="d51cf-148">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d51cf-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d51cf-149">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="d51cf-150">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d51cf-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d51cf-151">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d51cf-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d51cf-152">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d51cf-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d51cf-153">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="d51cf-153">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="d51cf-154">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="d51cf-154">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="d51cf-155">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d51cf-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="d51cf-156">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d51cf-156">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
