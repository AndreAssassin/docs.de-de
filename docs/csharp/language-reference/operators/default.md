---
title: 'default-Operator: C#-Referenz'
ms.custom: seodec18
description: Der default-Operator dient zum Erzeugen des Standardwerts eines Typs.
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796939"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="b57e1-103">default-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b57e1-103">default operator (C# reference)</span></span>

<span data-ttu-id="b57e1-104">Der `default`-Operator dient zum Erzeugen des [Standardwerts](../keywords/default-values-table.md) eines Typs.</span><span class="sxs-lookup"><span data-stu-id="b57e1-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="b57e1-105">Das Argument für den `default`-Operator muss der Name eines Typs oder ein Typparameter sein.</span><span class="sxs-lookup"><span data-stu-id="b57e1-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="b57e1-106">Im folgenden Beispiel wird die Verwendung des `default`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b57e1-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="b57e1-107">Außerdem verwenden Sie das Schlüsselwort `default` in der [`switch`-Anweisung](../keywords/switch.md) als standardmäßige case-Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b57e1-107">You also use the `default` keyword as the default case label within the [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="b57e1-108">Standardliteral</span><span class="sxs-lookup"><span data-stu-id="b57e1-108">default literal</span></span>

<span data-ttu-id="b57e1-109">Ab C# 7.1 können Sie das `default`-Literal verwenden, um den Standardwert eines Typs zu erzeugen, wenn der Compiler den Ausdruckstyp ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="b57e1-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="b57e1-110">Der `default`-Literalausdruck erzeugt den gleichen Wert wie der `default(T)`-Ausdruck, wobei `T` der abgeleitete Typ ist.</span><span class="sxs-lookup"><span data-stu-id="b57e1-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="b57e1-111">Sie können das `default`-Literal in den folgenden Fälle verwenden:</span><span class="sxs-lookup"><span data-stu-id="b57e1-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="b57e1-112">Bei der Zuweisung oder Initialisierung einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="b57e1-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="b57e1-113">Bei der Deklaration des Standardwerts eines optionalen Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="b57e1-113">In the declaration of the default value for an optional method parameter.</span></span>
- <span data-ttu-id="b57e1-114">Bei einem Methodenaufruf zum Bereitstellen eines Argumentwerts.</span><span class="sxs-lookup"><span data-stu-id="b57e1-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="b57e1-115">In einer `return`-Anweisung oder als Ausdruck in einem Ausdruckskörpermember.</span><span class="sxs-lookup"><span data-stu-id="b57e1-115">In a `return` statement or as an expression in an expression-bodied member.</span></span>

<span data-ttu-id="b57e1-116">Im folgenden Beispiel wird die Verwendung des `default`-Literals veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b57e1-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="b57e1-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b57e1-117">C# language specification</span></span>

<span data-ttu-id="b57e1-118">Weitere Informationen finden Sie im Abschnitt [Ausdrücke mit Standardwert](~/_csharplang/spec/expressions.md#default-value-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b57e1-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="b57e1-119">Weitere Informationen zum `default`-Literal finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="b57e1-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b57e1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b57e1-120">See also</span></span>

- [<span data-ttu-id="b57e1-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b57e1-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b57e1-122">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b57e1-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="b57e1-123">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="b57e1-123">Default values table</span></span>](../keywords/default-values-table.md)
