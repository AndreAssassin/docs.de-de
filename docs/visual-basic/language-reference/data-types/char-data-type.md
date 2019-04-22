---
title: Char-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: b50c902f69f7602dbad4663dc35bf0a2b932973f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832088"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="2a806-102">Char-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a806-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="2a806-103">Enthält unsignierten 16-Bit (2-Byte) Codepunkte im Bereich von 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="2a806-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="2a806-104">Jede *Codepunkt*, oder Zeichencode ein einzelnes Unicodezeichens darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a806-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a806-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a806-105">Remarks</span></span>  
 <span data-ttu-id="2a806-106">Verwenden der `Char` -Datentyp, wenn Sie nur eine einzige halten müssen Zeichen und ist nicht erforderlich, den Aufwand für `String`.</span><span class="sxs-lookup"><span data-stu-id="2a806-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="2a806-107">In einigen Fällen können Sie `Char()`, ein Array von `Char` Elemente, um mehrere Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a806-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="2a806-108">Der Standardwert von `Char` ist das Zeichen mit einem Codepunkt von 0.</span><span class="sxs-lookup"><span data-stu-id="2a806-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="2a806-109">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="2a806-109">Unicode Characters</span></span>  
 <span data-ttu-id="2a806-110">Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen, die auf einer US-Standardtastatur.</span><span class="sxs-lookup"><span data-stu-id="2a806-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="2a806-111">Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="2a806-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="2a806-112">Die zweite 128 Codepunkte (128 – 255) stellen die Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzenten, Währungssymbole und Bruchzahlen dar.</span><span class="sxs-lookup"><span data-stu-id="2a806-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="2a806-113">Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen, einschließlich weltweit Textzeichen, diakritische Zeichen und mathematischen und technischen Symbole.</span><span class="sxs-lookup"><span data-stu-id="2a806-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="2a806-114">Können Sie Methoden wie <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf eine `Char` Variable, um zu bestimmen, die Unicode-Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="2a806-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="2a806-115">Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="2a806-115">Type Conversions</span></span>  
 <span data-ttu-id="2a806-116">Konvertiert Visual Basic nicht direkt zwischen `Char` und numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="2a806-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="2a806-117">Können Sie die <xref:Microsoft.VisualBasic.Strings.Asc%2A> oder <xref:Microsoft.VisualBasic.Strings.AscW%2A> Funktion zum Konvertieren einer `Char` -Wert in ein `Integer` , die den Codepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a806-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="2a806-118">Können Sie die <xref:Microsoft.VisualBasic.Strings.Chr%2A> oder <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Funktion zum Konvertieren einer `Integer` Wert eine `Char` , diesen Codepunkt besitzt.</span><span class="sxs-lookup"><span data-stu-id="2a806-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="2a806-119">Wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)) aktiviert ist, muss auf ein einzelnes Zeichen Zeichenfolgenliteral als Identifikation des Literaltypzeichens angefügt der `Char` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="2a806-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="2a806-120">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2a806-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="2a806-121">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="2a806-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="2a806-122">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="2a806-122">**Negative Numbers.**</span></span> <span data-ttu-id="2a806-123">`Char` ein Typ ohne Vorzeichen und einen negativen Wert nicht darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="2a806-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="2a806-124">In jedem Fall sollten Sie nicht verwenden `Char` für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="2a806-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="2a806-125">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="2a806-125">**Interop Considerations.**</span></span> <span data-ttu-id="2a806-126">Wenn Sie eine mit Komponenten, die nicht für .NET Framework geschrieben wurden Schnittstelle z. B. Automatisierungs- oder COM-Objekte, denken Sie daran: Typen mit Zeichen eine andere Datenbreite (8 Bits) in anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="2a806-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="2a806-127">Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `Byte` anstelle von `Char` im neuen Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="2a806-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="2a806-128">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="2a806-128">**Widening.**</span></span> <span data-ttu-id="2a806-129">Die `Char` -Datentyp wird zu `String`.</span><span class="sxs-lookup"><span data-stu-id="2a806-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="2a806-130">Dies bedeutet, Sie können konvertieren `Char` zu `String` , ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="2a806-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="2a806-131">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="2a806-131">**Type Characters.**</span></span> <span data-ttu-id="2a806-132">Durch Anhängen des Literaltypzeichens `C` in eine Zeichenfolge für die einzelnen Zeichen Literal wird der `Char` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="2a806-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="2a806-133">`Char` verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="2a806-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="2a806-134">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="2a806-134">**Framework Type.**</span></span> <span data-ttu-id="2a806-135">Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="2a806-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a806-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a806-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="2a806-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="2a806-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2a806-138">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2a806-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="2a806-139">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="2a806-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2a806-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="2a806-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2a806-141">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="2a806-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="2a806-142">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="2a806-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
