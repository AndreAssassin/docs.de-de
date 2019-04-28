---
title: Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: fb5905c3c1124dd64371216bddda0a17235abdce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787191"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="49df6-102">Debuggen von Ausdrucksbäumen in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49df6-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="49df6-103">Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren.</span><span class="sxs-lookup"><span data-stu-id="49df6-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="49df6-104">Um einen schnellen Überblick über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die nur im Debugmodus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="49df6-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="49df6-105">Weitere Informationen zum Debugging finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="49df6-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>

<span data-ttu-id="49df6-106">Die `DebugView`-Eigenschaft stellt den Inhalt von Ausdrucksbaumstrukturen mithilfe von Visual Studio-Schnellansichten übersichtlicher dar.</span><span class="sxs-lookup"><span data-stu-id="49df6-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="49df6-107">Weitere Informationen finden Sie unter [Create Custom Visualizers (Erstellen benutzerdefinierter Schnellansichten)](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="49df6-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="49df6-108">So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur</span><span class="sxs-lookup"><span data-stu-id="49df6-108">To open a visualizer for an expression tree</span></span>

1. <span data-ttu-id="49df6-109">Klicken Sie auf das Lupensymbol, das in **DataTips** neben der `DebugView`-Eigenschaft einer Ausdrucksbaumstruktur, neben einem **Überwachungsfenster**, einem **Auto**- oder neben einem **Lokalfenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="49df6-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>

    <span data-ttu-id="49df6-110">Eine Liste von Schnellansichten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-110">A list of visualizers is displayed.</span></span>

2. <span data-ttu-id="49df6-111">Klicken Sie auf die gewünschte Schnellansicht.</span><span class="sxs-lookup"><span data-stu-id="49df6-111">Click the visualizer you want to use.</span></span>

<span data-ttu-id="49df6-112">Jeder Ausdruckstyp wird in der Schnellansicht angezeigt, wie in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49df6-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="49df6-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="49df6-113">ParameterExpressions</span></span>

<span data-ttu-id="49df6-114">Namen von <xref:System.Linq.Expressions.ParameterExpression>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="49df6-115">Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.</span><span class="sxs-lookup"><span data-stu-id="49df6-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-116">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="49df6-117">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-117">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="49df6-118">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-118">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="49df6-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="49df6-119">ConstantExpressions</span></span>
 <span data-ttu-id="49df6-120">Für <xref:System.Linq.Expressions.ConstantExpression>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-121">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="49df6-122">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-122">`DebugView` property</span></span>

    <span data-ttu-id="49df6-123">10</span><span class="sxs-lookup"><span data-stu-id="49df6-123">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="49df6-124">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-124">`DebugView` property</span></span>

    <span data-ttu-id="49df6-125">10D</span><span class="sxs-lookup"><span data-stu-id="49df6-125">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="49df6-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="49df6-126">BlockExpression</span></span>

<span data-ttu-id="49df6-127">Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in der `DebugInfo`-Eigenschaft in spitzen Klammern (\< und >) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="49df6-128">Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-129">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="49df6-130">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-130">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="49df6-131">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-131">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="49df6-132">LambdaExpression.</span><span class="sxs-lookup"><span data-stu-id="49df6-132">LambdaExpression</span></span>

<span data-ttu-id="49df6-133"><xref:System.Linq.Expressions.LambdaExpression>-Objekte werden zusammen mit ihren Delegattypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="49df6-134">Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="49df6-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-135">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="49df6-136">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-136">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="49df6-137">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-137">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="49df6-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="49df6-138">LabelExpression</span></span>

<span data-ttu-id="49df6-139">Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget>-Objekt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="49df6-140">Das `.Label`-Token gibt den Anfang der Bezeichnung an.</span><span class="sxs-lookup"><span data-stu-id="49df6-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="49df6-141">Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="49df6-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="49df6-142">Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="49df6-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-143">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="49df6-144">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-144">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="49df6-145">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-145">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="49df6-146">Überprüfte Operatoren</span><span class="sxs-lookup"><span data-stu-id="49df6-146">Checked Operators</span></span>

<span data-ttu-id="49df6-147">Überprüften Operatoren wird in der Ansicht das Symbol "#" vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="49df6-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="49df6-148">Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49df6-148">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="49df6-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="49df6-149">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="49df6-150">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-150">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="49df6-151">`DebugView` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="49df6-151">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="49df6-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49df6-152">See also</span></span>

- [<span data-ttu-id="49df6-153">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49df6-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="49df6-154">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="49df6-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="49df6-155">Erstellen benutzerdefinierter Schnellansichten</span><span class="sxs-lookup"><span data-stu-id="49df6-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
