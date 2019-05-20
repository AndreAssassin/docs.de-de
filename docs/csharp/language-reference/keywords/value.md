---
title: Kontextabhängiges value-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: cfd370df771998057fd421a0917b3e2fcd96d9f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633027"
---
# <a name="value-c-reference"></a><span data-ttu-id="c7591-102">value (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c7591-102">value (C# Reference)</span></span>

<span data-ttu-id="c7591-103">Das kontextabhängige Schlüsselwort `value` wird im Set-Accessor in normalen Eigenschaftendeklarationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7591-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="c7591-104">Es ähnelt einem Eingabeparameter einer Methode.</span><span class="sxs-lookup"><span data-stu-id="c7591-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="c7591-105">Das Wort `value` verweist auf den Wert, den Clientcode der Eigenschaft zuweisen möchte.</span><span class="sxs-lookup"><span data-stu-id="c7591-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="c7591-106">Im folgenden Beispiel verfügt `MyDerivedClass` über eine Eigenschaft mit dem Namen `Name`, die den Parameter `value` verwendet, um dem Unterstützungsfeld `name` eine neue Zeichenfolge zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c7591-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="c7591-107">Aus Sicht des Clientcodes ist der Vorgang als einfache Zuweisung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7591-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="c7591-108">Weitere Informationen zur Verwendung von `value` finden Sie unter [Eigenschaften](../../programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="c7591-108">For more information about the use of `value`, see [Properties](../../programming-guide/classes-and-structs/properties.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c7591-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c7591-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c7591-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7591-110">See also</span></span>

- [<span data-ttu-id="c7591-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c7591-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7591-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7591-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7591-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c7591-113">C# Keywords</span></span>](index.md)
