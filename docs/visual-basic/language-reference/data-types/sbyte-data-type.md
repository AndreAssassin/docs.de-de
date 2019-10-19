---
title: SByte-Datentyp (Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: a962200195002858257b92e92e0dd1383d4fb2d2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582514"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="e0e2b-102">SByte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0e2b-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="e0e2b-103">Enthält signierte 8-Bit-Ganzzahlen (1 Byte), die den Wert von-128 bis 127 über liegen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0e2b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0e2b-104">Remarks</span></span>

<span data-ttu-id="e0e2b-105">Verwenden Sie den `SByte`-Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von `Integer` oder sogar die halbe Daten Breite `Short` benötigen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="e0e2b-106">In einigen Fällen können die Common Language Runtime ihre `SByte` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="e0e2b-107">Der Standardwert von `SByte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="e0e2b-108">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="e0e2b-108">Literal assignments</span></span>

<span data-ttu-id="e0e2b-109">Sie können eine `SByte` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="e0e2b-110">Im folgenden Beispiel werden Ganzzahlen von-102, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, `SByte` Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="e0e2b-111">Für dieses Beispiel ist es erforderlich, dass Sie mit dem `/removeintchecks`-Compilerschalter kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="e0e2b-112">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="e0e2b-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="e0e2b-114">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="e0e2b-115">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="e0e2b-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e0e2b-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="e0e2b-117">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="e0e2b-118">Wenn ein Ganzzahlliteral kein Suffix aufweist, wird eine [ganze](integer-data-type.md) Zahl abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="e0e2b-119">Wenn das ganzzahlige Literale außerhalb des Bereichs des `Integer` Typs liegt, wird eine [lange](long-data-type.md) abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="e0e2b-120">Dies bedeutet, dass in den vorherigen Beispielen die numerischen Literale `0x9A` und `0b10011010` als 32-Bit-Ganzzahlen mit Vorzeichen mit einem Wert von 156 interpretiert werden, der <xref:System.SByte.MaxValue?displayProperty=nameWithType> überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e0e2b-121">Zur erfolgreichen Kompilierung von Code wie diesem, der einer `SByte` eine nicht dezimale Ganzzahl zuweist, können Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e0e2b-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="e0e2b-122">Deaktivieren Sie Überprüfungen der ganzzahligen Grenzen, indem Sie die Kompilierung mit dem `/removeintchecks`</span><span class="sxs-lookup"><span data-stu-id="e0e2b-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="e0e2b-123">Verwenden Sie ein [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) , um den Literalwert, den Sie dem `SByte` zuweisen möchten, explizit zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="e0e2b-124">Im folgenden Beispiel wird einem `SByte` ein negativer Literal`Short` Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="e0e2b-125">Beachten Sie, dass für negative Zahlen das höchst wertige Bit des großen Worts des numerischen Literals festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="e0e2b-126">Im vorliegenden Beispiel ist dies Bit 15 des literalen `Short` Werts.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="e0e2b-127">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="e0e2b-127">Programming tips</span></span>

- <span data-ttu-id="e0e2b-128">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="e0e2b-128">**CLS Compliance.**</span></span> <span data-ttu-id="e0e2b-129">Der `SByte`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="e0e2b-130">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="e0e2b-130">**Widening.**</span></span> <span data-ttu-id="e0e2b-131">Der `SByte`-Datentyp wird auf `Short`, `Integer`, `Long`, `Decimal`, `Single` und `Double` erweitert.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="e0e2b-132">Dies bedeutet, dass Sie `SByte` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="e0e2b-133">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="e0e2b-133">**Type Characters.**</span></span> <span data-ttu-id="e0e2b-134">`SByte` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="e0e2b-135">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="e0e2b-135">**Framework Type.**</span></span> <span data-ttu-id="e0e2b-136">Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="e0e2b-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0e2b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0e2b-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="e0e2b-138">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e0e2b-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e0e2b-139">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="e0e2b-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="e0e2b-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="e0e2b-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="e0e2b-141">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e0e2b-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="e0e2b-142">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e0e2b-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="e0e2b-143">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e0e2b-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="e0e2b-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="e0e2b-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
