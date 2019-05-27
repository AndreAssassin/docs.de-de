---
title: Syntax von DebugView-Eigenschaft (Visual Basic) verwendet wird
description: Beschreibt die spezielle Syntax, die durch die DebugView-Eigenschaft verwendet wird, um eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen zu erstellen.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196530"
---
# <a name="debugview-syntax"></a><span data-ttu-id="18a35-103">`DebugView`-Syntax</span><span class="sxs-lookup"><span data-stu-id="18a35-103">`DebugView` syntax</span></span> 

<span data-ttu-id="18a35-104">Die `DebugView` Eigenschaft (nur beim Debuggen verfügbar) bietet eine Darstellung der Zeichenfolge von Ausdrucksbaumstrukturen.</span><span class="sxs-lookup"><span data-stu-id="18a35-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="18a35-105">Die meisten der Syntax ist recht einfach zu verstehen. besondere Fälle werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="18a35-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="18a35-106">Jedes Beispiel folgt eine Comment-Block mit der `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="18a35-106">Each example is followed by a comment block containing the `DebugView`.</span></span> 

## <a name="parameterexpression"></a><span data-ttu-id="18a35-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="18a35-107">ParameterExpression</span></span>

<span data-ttu-id="18a35-108">Namen von <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="18a35-109">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="18a35-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="18a35-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-110">Examples</span></span>

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a><span data-ttu-id="18a35-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="18a35-111">ConstantExpressions</span></span>

<span data-ttu-id="18a35-112">Für <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="18a35-113">Für einige numerische Typen wird der Wert ein Suffix hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="18a35-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="18a35-114">Typ</span><span class="sxs-lookup"><span data-stu-id="18a35-114">Type</span></span> | <span data-ttu-id="18a35-115">Stichwort</span><span class="sxs-lookup"><span data-stu-id="18a35-115">Keyword</span></span> | <span data-ttu-id="18a35-116">Suffix</span><span class="sxs-lookup"><span data-stu-id="18a35-116">Suffix</span></span> |  
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="18a35-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="18a35-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="18a35-118">U</span><span class="sxs-lookup"><span data-stu-id="18a35-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="18a35-119">Long</span><span class="sxs-lookup"><span data-stu-id="18a35-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="18a35-120">L</span><span class="sxs-lookup"><span data-stu-id="18a35-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="18a35-121">ULong</span><span class="sxs-lookup"><span data-stu-id="18a35-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="18a35-122">UL</span><span class="sxs-lookup"><span data-stu-id="18a35-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="18a35-123">Double</span><span class="sxs-lookup"><span data-stu-id="18a35-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="18a35-124">D</span><span class="sxs-lookup"><span data-stu-id="18a35-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="18a35-125">Single</span><span class="sxs-lookup"><span data-stu-id="18a35-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="18a35-126">F</span><span class="sxs-lookup"><span data-stu-id="18a35-126">F</span></span> | 
| <xref:System.Decimal> | [<span data-ttu-id="18a35-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="18a35-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="18a35-128">M</span><span class="sxs-lookup"><span data-stu-id="18a35-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="18a35-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-129">Examples</span></span>

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a><span data-ttu-id="18a35-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="18a35-130">BlockExpression</span></span>

<span data-ttu-id="18a35-131">Wenn der Typ des eine <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> Objekt vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in spitzen Klammern angezeigt (`<` und `>`).</span><span class="sxs-lookup"><span data-stu-id="18a35-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="18a35-132">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="18a35-133">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-133">Examples</span></span>

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object), 
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a><span data-ttu-id="18a35-134">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="18a35-134">LambdaExpression</span></span>

<span data-ttu-id="18a35-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="18a35-136">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="18a35-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="18a35-137">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-137">Examples</span></span>

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a><span data-ttu-id="18a35-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="18a35-138">LabelExpression</span></span>

<span data-ttu-id="18a35-139">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="18a35-140">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="18a35-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="18a35-141">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="18a35-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="18a35-142">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="18a35-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="18a35-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-143">Examples</span></span>

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), 
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a><span data-ttu-id="18a35-144">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="18a35-144">Checked Operators</span></span>

<span data-ttu-id="18a35-145">Überprüfte Operatoren werden angezeigt, mit der `#` Ansicht das Symbol.</span><span class="sxs-lookup"><span data-stu-id="18a35-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="18a35-146">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18a35-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="18a35-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="18a35-147">Examples</span></span>

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```