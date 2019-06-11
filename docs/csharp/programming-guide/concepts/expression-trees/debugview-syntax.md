---
title: Syntax der DebugView-Eigenschaft (C#)
description: Beschreibt die spezielle Syntax, die von der DebugView-Eigenschaft verwendet wird, um eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen zu erzeugen.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: bc3fc579ed8031d818241f41ac728ef7e5be0b99
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690109"
---
# <a name="debugview-syntax"></a><span data-ttu-id="82af4-103">`DebugView`-Syntax</span><span class="sxs-lookup"><span data-stu-id="82af4-103">`DebugView` syntax</span></span>

<span data-ttu-id="82af4-104">Die `DebugView`-Eigenschaft (nur beim Debuggen verfügbar) bietet eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen.</span><span class="sxs-lookup"><span data-stu-id="82af4-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="82af4-105">Der größte Teil der Syntax ist recht einfach zu verstehen; einige Sonderfälle werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82af4-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="82af4-106">Jedem Beispiel folgt ein Blockkommentar, der die `DebugView` enthält.</span><span class="sxs-lookup"><span data-stu-id="82af4-106">Each example is followed by a block comment, containing the `DebugView`.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="82af4-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="82af4-107">ParameterExpression</span></span>

<span data-ttu-id="82af4-108">Namen von <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType>-Variablen werden mit einem `$`-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a `$` symbol at the beginning.</span></span>

<span data-ttu-id="82af4-109">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="82af4-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="82af4-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-110">Examples</span></span>

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a><span data-ttu-id="82af4-111">ConstantExpression</span><span class="sxs-lookup"><span data-stu-id="82af4-111">ConstantExpression</span></span>

<span data-ttu-id="82af4-112">Für <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="82af4-113">Für numerische Typen, die über Standardsuffixe als C#-Literale verfügen, wird das Suffix zum Wert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="82af4-113">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="82af4-114">Die folgende Tabelle zeigt die verschiedenen numerischen Typen und ihre zugeordneten Suffixe.</span><span class="sxs-lookup"><span data-stu-id="82af4-114">The following table shows the suffixes associated with various numeric types.</span></span>

| <span data-ttu-id="82af4-115">Typ</span><span class="sxs-lookup"><span data-stu-id="82af4-115">Type</span></span> | <span data-ttu-id="82af4-116">Stichwort</span><span class="sxs-lookup"><span data-stu-id="82af4-116">Keyword</span></span> | <span data-ttu-id="82af4-117">Suffix</span><span class="sxs-lookup"><span data-stu-id="82af4-117">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="82af4-118">uint</span><span class="sxs-lookup"><span data-stu-id="82af4-118">uint</span></span>](../../../language-reference/keywords/uint.md) | <span data-ttu-id="82af4-119">U</span><span class="sxs-lookup"><span data-stu-id="82af4-119">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="82af4-120">long</span><span class="sxs-lookup"><span data-stu-id="82af4-120">long</span></span>](../../../language-reference/keywords/long.md) | <span data-ttu-id="82af4-121">L</span><span class="sxs-lookup"><span data-stu-id="82af4-121">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="82af4-122">ulong</span><span class="sxs-lookup"><span data-stu-id="82af4-122">ulong</span></span>](../../../language-reference/keywords/ulong.md) | <span data-ttu-id="82af4-123">UL</span><span class="sxs-lookup"><span data-stu-id="82af4-123">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="82af4-124">double</span><span class="sxs-lookup"><span data-stu-id="82af4-124">double</span></span>](../../../language-reference/keywords/double.md) | <span data-ttu-id="82af4-125">D</span><span class="sxs-lookup"><span data-stu-id="82af4-125">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="82af4-126">float</span><span class="sxs-lookup"><span data-stu-id="82af4-126">float</span></span>](../../../language-reference/keywords/float.md) | <span data-ttu-id="82af4-127">F</span><span class="sxs-lookup"><span data-stu-id="82af4-127">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="82af4-128">decimal</span><span class="sxs-lookup"><span data-stu-id="82af4-128">decimal</span></span>](../../../language-reference/keywords/decimal.md) | <span data-ttu-id="82af4-129">M</span><span class="sxs-lookup"><span data-stu-id="82af4-129">M</span></span> |

### <a name="examples"></a><span data-ttu-id="82af4-130">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-130">Examples</span></span>

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a><span data-ttu-id="82af4-131">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="82af4-131">BlockExpression</span></span>

<span data-ttu-id="82af4-132">Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in spitzen Klammern (`<` und `>`) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-132">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="82af4-133">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-133">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="82af4-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-134">Examples</span></span>

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a><span data-ttu-id="82af4-135">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="82af4-135">LambdaExpression</span></span>

<span data-ttu-id="82af4-136"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-136"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="82af4-137">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="82af4-137">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="82af4-138">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-138">Examples</span></span>

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a><span data-ttu-id="82af4-139">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="82af4-139">LabelExpression</span></span>

<span data-ttu-id="82af4-140">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-140">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="82af4-141">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="82af4-141">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="82af4-142">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82af4-142">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="82af4-143">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="82af4-143">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="82af4-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-144">Examples</span></span>

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a><span data-ttu-id="82af4-145">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="82af4-145">Checked Operators</span></span>

<span data-ttu-id="82af4-146">Überprüften Operatoren wird in der Ansicht das `#`-Symbol vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="82af4-146">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="82af4-147">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82af4-147">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="82af4-148">Beispiele</span><span class="sxs-lookup"><span data-stu-id="82af4-148">Examples</span></span>

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
