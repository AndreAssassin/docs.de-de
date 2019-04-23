---
title: '&amp;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310043"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="930af-102">&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="930af-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="930af-103">Der Operator `&` wird in zwei Formen unterstützt: als unärer address-of-Operator oder als binärer logischer Operator.</span><span class="sxs-lookup"><span data-stu-id="930af-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="930af-104">Unärer address-of-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-104">Unary address-of operator</span></span>

<span data-ttu-id="930af-105">Der unäre `&`-Operator gibt die Adresse seines Operanden zurück.</span><span class="sxs-lookup"><span data-stu-id="930af-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="930af-106">Weitere Informationen finden Sie unter [Gewusst wie: Abrufen der Adresse einer Variablen](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="930af-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="930af-107">Der address-of-Operator `&` erfordert [unsicheren](../keywords/unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="930af-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="930af-108">Ganzzahliger bitweiser logischer AND-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="930af-109">Für ganzzahlige Datentypen berechnet der `&`-Operator die bitweise logische AND-Operation der Operanden:</span><span class="sxs-lookup"><span data-stu-id="930af-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="930af-110">Im Beispiel oben werden die [in C# 7.0 eingeführten](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) und [in C# 7.2 erweiterten](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals) binären Literale verwendet.</span><span class="sxs-lookup"><span data-stu-id="930af-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="930af-111">Da die Operationen für ganzzahlige Datentypen im Allgemeinen für Enumerationstypen zulässig sind, unterstützt der `&`-Operator auch [enum](../keywords/enum.md)-Operanden.</span><span class="sxs-lookup"><span data-stu-id="930af-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="930af-112">Boolescher logischer AND-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-112">Boolean logical AND operator</span></span>

<span data-ttu-id="930af-113">Für [bool](../keywords/bool.md)-Operanden berechnet der `&`-Operator die logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="930af-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="930af-114">Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="930af-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="930af-115">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="930af-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="930af-116">Der `&`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `false` sein muss.</span><span class="sxs-lookup"><span data-stu-id="930af-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="930af-117">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="930af-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="930af-118">Der [bedingte AND-Operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="930af-118">The [conditional AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="930af-119">Für Operanden, die NULL-Werte zulassen, ist das Verhalten des `&`-Operators konsistent mit der dreiwertigen Logik von SQL.</span><span class="sxs-lookup"><span data-stu-id="930af-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="930af-120">Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="930af-120">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="930af-121">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="930af-121">Operator overloadability</span></span>

<span data-ttu-id="930af-122">Benutzerdefinierte Typen können den binären `&`-Operator [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="930af-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="930af-123">Wenn ein binärer `&`-Operator überladen ist, wird der [AND-Zuweisungsoperator](and-assignment-operator.md) `&=` auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="930af-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="930af-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="930af-124">C# language specification</span></span>

<span data-ttu-id="930af-125">Weitere Informationen finden Sie in den Abschnitten [Der address-of-Operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) und [Logische Operatoren](~/_csharplang/spec/expressions.md#logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="930af-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="930af-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="930af-126">See also</span></span>

- [<span data-ttu-id="930af-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="930af-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="930af-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="930af-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="930af-129">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="930af-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="930af-130">Logische boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="930af-130">Boolean logical operators</span></span>](boolean-logical-operators.md)
- [<span data-ttu-id="930af-131">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="930af-131">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="930af-132">|-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-132">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="930af-133">^-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-133">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="930af-134">~-Operator</span><span class="sxs-lookup"><span data-stu-id="930af-134">~ operator</span></span>](bitwise-complement-operator.md)
