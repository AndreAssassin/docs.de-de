---
title: char-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: b58730d945582ded7b76fcd5c4c65bc1dd9324da
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661459"
---
# <a name="char-c-reference"></a><span data-ttu-id="aeea3-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="aeea3-102">char (C# Reference)</span></span>

<span data-ttu-id="aeea3-103">Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=nameWithType>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeea3-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="aeea3-104">Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).</span><span class="sxs-lookup"><span data-stu-id="aeea3-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="aeea3-105">Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.</span><span class="sxs-lookup"><span data-stu-id="aeea3-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="aeea3-106">Typ</span><span class="sxs-lookup"><span data-stu-id="aeea3-106">Type</span></span>|<span data-ttu-id="aeea3-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="aeea3-107">Range</span></span>|<span data-ttu-id="aeea3-108">Größe</span><span class="sxs-lookup"><span data-stu-id="aeea3-108">Size</span></span>|<span data-ttu-id="aeea3-109">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="aeea3-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="aeea3-110">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="aeea3-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="aeea3-111">Ein Unicode-Zeichen (16 Bit)</span><span class="sxs-lookup"><span data-stu-id="aeea3-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="aeea3-112">Literale</span><span class="sxs-lookup"><span data-stu-id="aeea3-112">Literals</span></span>

<span data-ttu-id="aeea3-113">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="aeea3-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="aeea3-114">Sie können auch die ganzzahligen Zeichencodes umwandeln.</span><span class="sxs-lookup"><span data-stu-id="aeea3-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="aeea3-115">Im folgenden Beispiel werden vier `char`-Variablen mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="aeea3-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="aeea3-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="aeea3-116">Conversions</span></span>

<span data-ttu-id="aeea3-117">Ein `char` kann implizit in ein [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) oder [decimal](../builtin-types/floating-point-numeric-types.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="aeea3-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="aeea3-118">Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="aeea3-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="aeea3-119">Der Typ <xref:System.Char?displayProperty=nameWithType> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="aeea3-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="aeea3-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="aeea3-120">C# language specification</span></span>  

<span data-ttu-id="aeea3-121">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="aeea3-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="aeea3-122">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="aeea3-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeea3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aeea3-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="aeea3-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="aeea3-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="aeea3-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="aeea3-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="aeea3-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="aeea3-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="aeea3-127">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="aeea3-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="aeea3-128">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="aeea3-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="aeea3-129">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="aeea3-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="aeea3-130">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="aeea3-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="aeea3-131">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="aeea3-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
- [<span data-ttu-id="aeea3-132">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="aeea3-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
