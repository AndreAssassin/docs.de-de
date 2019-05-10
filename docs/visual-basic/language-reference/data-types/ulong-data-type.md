---
title: ULong-Datentyp (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 7f8a19e2e4395e43aa99b6ff63536fbbbc26cb2a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646964"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="95450-102">ULong-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95450-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="95450-103">64-Bit (8 Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 18.446.744.073.709.551.615 enthält (mehr als 1,84 Mal 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="95450-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95450-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95450-104">Remarks</span></span>

<span data-ttu-id="95450-105">Verwenden der `ULong` Datentyp zu groß für die Binärdaten enthält `UInteger`, oder die größten möglichen unsigned Integer-Werte.</span><span class="sxs-lookup"><span data-stu-id="95450-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="95450-106">Der Standardwert von `ULong` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="95450-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="95450-107">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="95450-107">Literal assignments</span></span>

<span data-ttu-id="95450-108">Sie können deklarieren und initialisieren eine `ULong` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="95450-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="95450-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="95450-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="95450-110">Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="95450-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="95450-111">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="95450-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="95450-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="95450-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="95450-113">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="95450-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="95450-114">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="95450-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="95450-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95450-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="95450-116">Numerische Literale können auch einschließen, die `UL` oder `ul` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `ULong` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="95450-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="95450-117">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="95450-117">Programming tips</span></span>
  
- <span data-ttu-id="95450-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="95450-118">**Negative Numbers.**</span></span> <span data-ttu-id="95450-119">Da `ULong` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen.</span><span class="sxs-lookup"><span data-stu-id="95450-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="95450-120">Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `ULong`, konvertiert den Ausdruck, der Visual Basic `Decimal` erste.</span><span class="sxs-lookup"><span data-stu-id="95450-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
- <span data-ttu-id="95450-121">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="95450-121">**CLS Compliance.**</span></span> <span data-ttu-id="95450-122">Die `ULong` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95450-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
- <span data-ttu-id="95450-123">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="95450-123">**Interop Considerations.**</span></span> <span data-ttu-id="95450-124">Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, die Typen wie `ulong` kann in anderen Umgebungen über eine andere Datenbreite (32 Bit) verfügen.</span><span class="sxs-lookup"><span data-stu-id="95450-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="95450-125">Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UInteger` anstelle von `ULong` in verwaltetem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="95450-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="95450-126">Automation unterstützt darüber hinaus keine 64-Bit-Ganzzahlen auf Windows 95, Windows 98, Windows ME oder Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="95450-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="95450-127">Sie können keine übergeben, eine Visual Basic `ULong` Argument an eine Automatisierungskomponente auf diesen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="95450-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
- <span data-ttu-id="95450-128">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="95450-128">**Widening.**</span></span> <span data-ttu-id="95450-129">Die `ULong` -Datentyp wird zu `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="95450-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="95450-130">Dies bedeutet, Sie können konvertieren `ULong` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="95450-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="95450-131">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="95450-131">**Type Characters.**</span></span> <span data-ttu-id="95450-132">Durch Anhängen des Literaltypzeichens `UL` an ein Literal wird der `ULong` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="95450-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="95450-133">`ULong` verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="95450-133">`ULong` has no identifier type character.</span></span>
  
- <span data-ttu-id="95450-134">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="95450-134">**Framework Type.**</span></span> <span data-ttu-id="95450-135">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="95450-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95450-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95450-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="95450-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="95450-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="95450-138">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="95450-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="95450-139">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="95450-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="95450-140">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="95450-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="95450-141">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="95450-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
