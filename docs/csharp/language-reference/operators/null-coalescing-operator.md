---
title: ?? und ??= (Operatoren) – C#-Referenz
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 1e94038a41a6a6cc19be6c67bff2891397793fb3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924682"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="92f1d-103">??</span><span class="sxs-lookup"><span data-stu-id="92f1d-103">??</span></span> <span data-ttu-id="92f1d-104">und ??= (Operatoren) – C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92f1d-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="92f1d-105">Der NULL-Zusammenfügungsoperator `??` gibt den Wert des linken Operanden zurück, wenn dieser nicht `null` ist. Andernfalls wertet der Operator den rechten Operanden aus und gibt dessen Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="92f1d-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="92f1d-106">Der `??`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="92f1d-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="92f1d-107">Ab C# 8.0 können Sie den NULL-Sammelzuweisungsoperator `??=` verwenden, um den Wert des rechten Operanden dem linken Operanden nur dann zuzuweisen, wenn die Auswertung des linken Operanden `null` ergibt.</span><span class="sxs-lookup"><span data-stu-id="92f1d-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="92f1d-108">Der `??=`-Operator wertet seinen rechten Operanden nicht aus, wenn der linke Operand auf einen Wert ungleich NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="92f1d-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="92f1d-109">Der linke Operand des `??=`-Operators muss eine Variable, eine [Eigenschaft](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexer](../../programming-guide/indexers/index.md)-Element sein.</span><span class="sxs-lookup"><span data-stu-id="92f1d-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span> <span data-ttu-id="92f1d-110">Weitere Informationen zur NULL-Sammelzuweisung finden Sie im [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="92f1d-110">For more information about null-coalescing assignment, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

<span data-ttu-id="92f1d-111">In C# 7.3 und früher muss der Typ des linken Operanden des `??`-Operators entweder ein Verweistyp oder ein [auf NULL festlegbarer Werttyp](../../programming-guide/nullable-types/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="92f1d-111">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a reference type or a [nullable value type](../../programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="92f1d-112">Ab C# 8.0 wird diese Anforderung durch Folgendes ersetzt: der Typ des linken Operanden der Operatoren `??` und `??=` kann kein Werttyp sein, der nicht auf NULL festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="92f1d-112">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="92f1d-113">Das heißt, Sie können die NULL-Sammeloperatoren mit uneingeschränkten Typparametern ab C# 8.0 verwenden:</span><span class="sxs-lookup"><span data-stu-id="92f1d-113">In particular, you can use the null-coalescing operators with unconstrained type parameters in C# 8.0 and later:</span></span>

[!code-csharp[unconstrained type parameter](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="92f1d-114">Die NULL-Sammeloperatoren sind rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="92f1d-114">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="92f1d-115">Das heißt, Ausdrücke wie</span><span class="sxs-lookup"><span data-stu-id="92f1d-115">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="92f1d-116">werden wie folgt ausgewertet</span><span class="sxs-lookup"><span data-stu-id="92f1d-116">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="92f1d-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="92f1d-117">Examples</span></span>

<span data-ttu-id="92f1d-118">Die Operatoren `??` und `??=` können in folgenden Szenarios nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="92f1d-118">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="92f1d-119">In Ausdrücken mit den [NULL-bedingten Operatoren „?.“ und „?[]“](member-access-operators.md#null-conditional-operators--and-) können Sie den NULL-Zusammenfügungsoperator verwenden, um einen alternativen Ausdruck zum Auswerten für den Fall bereitzustellen, dass das Ergebnis des NULL-bedingten Vorgangs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="92f1d-119">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="92f1d-120">Wenn Sie mit [Nullable-Werttypen](../../programming-guide/nullable-types/index.md) arbeiten und den Wert eines zugrunde liegenden Werttyps bereitstellen müssen, verwenden Sie den NULL-Zusammenfügungsoperator, um den Wert für den Fall anzugeben, dass der Wert eines Nullable-Typs `null` ist:</span><span class="sxs-lookup"><span data-stu-id="92f1d-120">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="92f1d-121">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwenden werden soll, falls der Wert des Nullable-Typs `null` lautet, der Standardwert des zugrunde liegenden Werttyps sein soll.</span><span class="sxs-lookup"><span data-stu-id="92f1d-121">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="92f1d-122">Ab C# 7.0 können Sie einen [`throw`Ausdruck](../keywords/throw.md#the-throw-expression) als rechten Operanden des NULL-Zusammenfügungsoperators verwenden, um den Code für die Überprüfung der Argumente präziser zu fassen:</span><span class="sxs-lookup"><span data-stu-id="92f1d-122">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="92f1d-123">Das oben stehende Beispiel veranschaulicht auch, wie Sie [Ausdruckskörpermember](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) verwenden, um eine Eigenschaft zu definieren.</span><span class="sxs-lookup"><span data-stu-id="92f1d-123">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="92f1d-124">Ab C# 8.0 können Sie den `??=`-Operator zum Ersetzen des folgenden Codes verwenden</span><span class="sxs-lookup"><span data-stu-id="92f1d-124">Starting with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="92f1d-125">durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="92f1d-125">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="92f1d-126">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="92f1d-126">Operator overloadability</span></span>

<span data-ttu-id="92f1d-127">Die Operatoren `??` und `??=` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="92f1d-127">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="92f1d-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="92f1d-128">C# language specification</span></span>

<span data-ttu-id="92f1d-129">Weitere Informationen über den `??`-Operator finden Sie im Abschnitt [NULL-Sammeloperatoren](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="92f1d-129">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92f1d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92f1d-130">See also</span></span>

- [<span data-ttu-id="92f1d-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92f1d-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="92f1d-132">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="92f1d-132">C# operators</span></span>](index.md)
- <span data-ttu-id="92f1d-133">[?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="92f1d-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="92f1d-134">?:-Operator</span><span class="sxs-lookup"><span data-stu-id="92f1d-134">?: operator</span></span>](conditional-operator.md)
