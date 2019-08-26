---
title: checked-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 69bd8cc95012533a6be279b04dc883a56f6f78ea
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605915"
---
# <a name="checked-c-reference"></a><span data-ttu-id="b4d35-102">checked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b4d35-102">checked (C# Reference)</span></span>

<span data-ttu-id="b4d35-103">Das Schlüsselwort `checked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen explizit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b4d35-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="b4d35-104">Standardmäßig bewirkt ein Ausdruck, der nur konstante Werte enthält, einen Compilerfehler, wenn der Ausdruck einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps liegt.</span><span class="sxs-lookup"><span data-stu-id="b4d35-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="b4d35-105">Wenn der Ausdruck einen oder mehrere nicht konstante Werte enthält, erkennt der Compiler den Überlauf nicht.</span><span class="sxs-lookup"><span data-stu-id="b4d35-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="b4d35-106">Die Auswertung des Ausdrucks, der im folgenden Beispiel `i2` zugewiesen ist, verursacht keinen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="b4d35-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="b4d35-107">Standardmäßig werden diese nicht konstanten Ausdrücke zur Laufzeit auch nicht auf Überläufe überprüft und lösen keine Überlaufausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="b4d35-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="b4d35-108">Das vorherige Beispiel zeigt -2,147,483,639 als Summe von zwei ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="b4d35-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="b4d35-109">Die Überlaufüberprüfung kann durch Compileroptionen, Umgebungskonfiguration oder Verwendung des `checked`-Schlüsselworts aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b4d35-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="b4d35-110">In den folgenden Beispielen wird veranschaulicht, wie Sie einen `checked`-Ausdruck oder einen `checked`-Block verwenden, um den Überlauf zu erkennen, der von der vorherigen Summe zur Laufzeit erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="b4d35-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="b4d35-111">In beiden Beispielen wird eine Überlaufausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b4d35-111">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="b4d35-112">Das [unchecked](./unchecked.md)-Schlüsselwort kann verwendet werden, um die Überlaufüberprüfung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b4d35-112">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="b4d35-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4d35-113">Example</span></span>

<span data-ttu-id="b4d35-114">Dieses Beispiel zeigt, wie mit `checked` die Überlaufüberprüfung zur Laufzeit aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b4d35-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="b4d35-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b4d35-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b4d35-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d35-116">See also</span></span>

- [<span data-ttu-id="b4d35-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b4d35-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4d35-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b4d35-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b4d35-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b4d35-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b4d35-120">AKtiviert und nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="b4d35-120">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="b4d35-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="b4d35-121">unchecked</span></span>](./unchecked.md)
