---
title: Function-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: dffe67d1c31b0fe7c037839ba0588793a461f276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638055"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="4cbea-102">Function-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cbea-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="4cbea-103">Deklariert den Namen, Parameter und Code, definieren eine `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="4cbea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cbea-104">Syntax</span></span>

```
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="4cbea-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4cbea-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="4cbea-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-106">Optional.</span></span> <span data-ttu-id="4cbea-107">Finden Sie unter [Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="4cbea-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-108">Optional.</span></span> <span data-ttu-id="4cbea-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4cbea-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="4cbea-110">Public</span><span class="sxs-lookup"><span data-stu-id="4cbea-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="4cbea-111">Protected</span><span class="sxs-lookup"><span data-stu-id="4cbea-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="4cbea-112">Friend</span><span class="sxs-lookup"><span data-stu-id="4cbea-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="4cbea-113">Private</span><span class="sxs-lookup"><span data-stu-id="4cbea-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="4cbea-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="4cbea-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="4cbea-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="4cbea-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="4cbea-116">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="4cbea-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-117">Optional.</span></span> <span data-ttu-id="4cbea-118">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4cbea-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="4cbea-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="4cbea-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="4cbea-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="4cbea-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="4cbea-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="4cbea-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="4cbea-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4cbea-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="4cbea-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4cbea-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="4cbea-124">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-124">Optional.</span></span> <span data-ttu-id="4cbea-125">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="4cbea-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-126">Optional.</span></span> <span data-ttu-id="4cbea-127">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="4cbea-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-128">Optional.</span></span> <span data-ttu-id="4cbea-129">Finden Sie unter [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="4cbea-130">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-130">Optional.</span></span> <span data-ttu-id="4cbea-131">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="4cbea-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-132">Required.</span></span> <span data-ttu-id="4cbea-133">Der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4cbea-133">Name of the procedure.</span></span> <span data-ttu-id="4cbea-134">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="4cbea-135">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-135">Optional.</span></span> <span data-ttu-id="4cbea-136">Liste der Parameter vom Typ für eine generische Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4cbea-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="4cbea-137">Finden Sie unter [Liste](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="4cbea-138">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-138">Optional.</span></span> <span data-ttu-id="4cbea-139">Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellt.</span><span class="sxs-lookup"><span data-stu-id="4cbea-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="4cbea-140">Finden Sie unter [Parameterliste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="4cbea-141">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="4cbea-142">Der Datentyp des von dieser Prozedur zurückgegebenen Werts.</span><span class="sxs-lookup"><span data-stu-id="4cbea-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="4cbea-143">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-143">Optional.</span></span> <span data-ttu-id="4cbea-144">Gibt an, dass diese Prozedur, eine oder mehrere implementiert `Function` Prozeduren, die jeweils in einer Schnittstelle implementiert, die von dieser Prozedur enthaltenen Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="4cbea-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="4cbea-145">Finden Sie unter [Anweisung implementiert](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="4cbea-146">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4cbea-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4cbea-147">Liste der zu implementierenden `Function`-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="4cbea-148">Jede `implementedprocedure` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="4cbea-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="4cbea-149">Segment</span><span class="sxs-lookup"><span data-stu-id="4cbea-149">Part</span></span>|<span data-ttu-id="4cbea-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cbea-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="4cbea-151">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-151">Required.</span></span> <span data-ttu-id="4cbea-152">Name einer Schnittstelle implementiert, die von dieser Prozedur der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="4cbea-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="4cbea-153">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-153">Required.</span></span> <span data-ttu-id="4cbea-154">Name, wodurch die Prozedur in `interface` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4cbea-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="4cbea-155">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-155">Optional.</span></span> <span data-ttu-id="4cbea-156">Gibt an, dass dieses Verfahren auf eine oder mehrere bestimmte Ereignisse verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4cbea-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="4cbea-157">Finden Sie unter [behandelt](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="4cbea-158">Erforderlich, wenn `Handles` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4cbea-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="4cbea-159">Liste der Ereignisse, die diese Prozedur verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4cbea-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="4cbea-160">Jede `eventspecifier` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="4cbea-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="4cbea-161">Segment</span><span class="sxs-lookup"><span data-stu-id="4cbea-161">Part</span></span>|<span data-ttu-id="4cbea-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cbea-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="4cbea-163">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-163">Required.</span></span> <span data-ttu-id="4cbea-164">Die Objektvariable deklariert mit dem Datentyp der Klasse oder Struktur, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="4cbea-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="4cbea-165">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-165">Required.</span></span> <span data-ttu-id="4cbea-166">Der Name des Ereignisses, die diese Prozedur verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4cbea-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="4cbea-167">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4cbea-167">Optional.</span></span> <span data-ttu-id="4cbea-168">Der Block von Anweisungen, die in diesem Verfahren ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4cbea-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="4cbea-169">Beendet die Definition dieses Verfahrens.</span><span class="sxs-lookup"><span data-stu-id="4cbea-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cbea-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cbea-170">Remarks</span></span>

<span data-ttu-id="4cbea-171">Der gesamte ausführbarer Code muss innerhalb einer Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="4cbea-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="4cbea-172">Jede Prozedur, wird im Gegenzug deklariert, innerhalb einer Klasse, eine Struktur oder ein Modul, das als die enthaltende Klasse, Struktur oder Modul bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="4cbea-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="4cbea-173">Verwenden, um einen Wert an den aufrufenden Code zurückgeben, eine `Function` Prozedur; verwenden Sie andernfalls eine `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="4cbea-174">Definieren einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4cbea-174">Defining a Function</span></span>

<span data-ttu-id="4cbea-175">Sie können definieren, eine `Function` Prozedur nur auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="4cbea-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="4cbea-176">Aus diesem Grund muss der Deklarationskontext für eine Funktion eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle und eine Quelldatei, einem Namespace, eine Prozedur oder einen Block nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="4cbea-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="4cbea-177">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="4cbea-178">`Function` Prozeduren standardmäßig öffentlichen Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="4cbea-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="4cbea-179">Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="4cbea-180">Ein `Function` Prozedur deklariert den Datentyp des Werts, der die Prozedur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4cbea-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="4cbea-181">Sie können einen beliebigen Datentyp aufweisen oder den Namen der eine Enumeration, eine Struktur, eine Klasse oder einer Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="4cbea-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="4cbea-182">Wenn Sie nicht angeben der `returntype` -Parameter der Prozedur zurückgegebene `Object`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="4cbea-183">Wenn die Prozedur verwendet die `Implements` -Schlüsselwort, die enthaltende Klasse oder Struktur müssen Sie auch eine `Implements` Anweisung sofort nach der `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4cbea-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4cbea-184">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="4cbea-185">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Function` (in `definedname`) muss nicht mit den Namen dieses Verfahrens übereinstimmen (im `name`).</span><span class="sxs-lookup"><span data-stu-id="4cbea-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="4cbea-186">Sie können Lambda-Ausdrücke verwenden, Funktion Ausdrücke Inline definieren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="4cbea-187">Weitere Informationen finden Sie unter [Funktionsausdruck](../../../visual-basic/language-reference/operators/function-expression.md) und [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="4cbea-188">Zurückgeben aus einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4cbea-188">Returning from a Function</span></span>

<span data-ttu-id="4cbea-189">Wenn die `Function` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgesetzt, mit der Anweisung, die die Anweisung folgt, die die Prozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="4cbea-190">Um einen Wert aus einer Funktion zurückgeben, Sie können den Namen der Funktion den Wert zuweisen oder nehmen Sie diese in einem `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4cbea-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="4cbea-191">Die `Return` Anweisung gleichzeitig weist den Rückgabewert und beendet die Funktion, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4cbea-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="4cbea-192">Im folgende Beispiel weist den zurückgegeben Wert den Namen der Funktion `myFunction` und verwendet dann die `Exit Function` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4cbea-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="4cbea-193">Die `Exit Function` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung aus einem `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="4cbea-194">Eine beliebige Anzahl von `Exit Function` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Function` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="4cbea-195">Bei Verwendung von `Exit Function` ohne Zuweisen eines Werts zur `name`, die Prozedur gibt zurück, der Standardwert für den Datentyp, der im angegebenen `returntype`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="4cbea-196">Wenn `returntype` nicht angegeben ist, gibt die Prozedur `Nothing`, dies ist der Standardwert für `Object`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="4cbea-197">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="4cbea-197">Calling a Function</span></span>

<span data-ttu-id="4cbea-198">Rufen Sie eine `Function` Verfahren mit den Prozedurnamen, gefolgt von der Argumentliste in Klammern ein, in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4cbea-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="4cbea-199">Sie können die Klammern weglassen, nur dann, wenn Sie Argumente angeben, werden nicht.</span><span class="sxs-lookup"><span data-stu-id="4cbea-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="4cbea-200">Allerdings ist der Code besser lesbar, wenn Sie immer die Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="4cbea-201">Rufen Sie eine `Function` Prozedur, die die gleiche Weise, dass Sie eine beliebige Bibliothek aufrufen, wie z. B. Funktion `Sqrt`, `Cos`, oder `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="4cbea-202">Sie können auch eine Funktion aufrufen, mit der `Call` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4cbea-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="4cbea-203">In diesem Fall wird der Rückgabewert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4cbea-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="4cbea-204">Verwenden der `Call` Schlüsselwort wird nicht in den meisten Fällen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="4cbea-205">Weitere Informationen finden Sie unter [Call-Anweisung](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="4cbea-206">Visual Basic werden manchmal neu angeordnet, arithmetische Ausdrücke, um die interne Effizienz steigern.</span><span class="sxs-lookup"><span data-stu-id="4cbea-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="4cbea-207">Aus diesem Grund sollten Sie nicht verwenden eine `Function` Prozedur in einem arithmetischen Ausdruck, wenn die Funktion den Wert der Variablen im selben Ausdruck geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4cbea-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="4cbea-208">Asynchrone Funktionen</span><span class="sxs-lookup"><span data-stu-id="4cbea-208">Async Functions</span></span>

<span data-ttu-id="4cbea-209">Die *Async* Feature können Sie zum Aufrufen von asynchroner Funktionen ohne explizite Rückrufe oder den Code manuell über mehrere Funktionen oder Lambdaausdrücke teilen.</span><span class="sxs-lookup"><span data-stu-id="4cbea-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="4cbea-210">Wenn Sie eine Funktion mit kennzeichnen die [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer verwenden, können Sie die ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4cbea-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="4cbea-211">Wenn Steuerung erreicht eine `Await` Ausdruck in der `Async` -Funktion, die Steuerung an den Aufrufer zurückgegeben und Ausführung der Funktion wird angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4cbea-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="4cbea-212">Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4cbea-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="4cbea-213">Ein `Async` Prozedur an den Aufrufer zurückgegeben, wenn entweder das erste erwartete Objekt gefunden wird, die noch nicht abgeschlossen ist, oder es Ruft ab, an das Ende der `Async` Verfahren, welches Ereignis zuerst eintritt.</span><span class="sxs-lookup"><span data-stu-id="4cbea-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="4cbea-214">Ein `Async` Funktion kann einen Rückgabetyp haben <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="4cbea-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="4cbea-215">Ein Beispiel für eine `Async` Funktion, die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601> finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="4cbea-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="4cbea-216">Ein `Async` Funktion kann nicht deklariert keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="4cbea-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="4cbea-217">Ein [Sub-Anweisung](sub-statement.md) können auch markiert werden, mit der `Async` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="4cbea-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="4cbea-218">Dies wird hauptsächlich für Ereignishandler verwendet, in dem ein Wert kann nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4cbea-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="4cbea-219">Ein `Async` `Sub` Prozedur kann nicht abgewartet werden, und der Aufrufer eine `Async` `Sub` Prozedur kann keine Ausnahmen auffangen, die ausgelöst werden, indem die `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="4cbea-220">Weitere Informationen zu `Async` -Funktionen finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Ablaufsteuerung in asynchronen Programmen](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), und [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="4cbea-221">Iteratorfunktionen</span><span class="sxs-lookup"><span data-stu-id="4cbea-221">Iterator Functions</span></span>

<span data-ttu-id="4cbea-222">Ein *Iterator* Funktion führt eine benutzerdefinierte Iteration durch eine Auflistung, z. B. eine Liste oder ein Array.</span><span class="sxs-lookup"><span data-stu-id="4cbea-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="4cbea-223">Eine Iteratorfunktion verwendet die [Yield](yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4cbea-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="4cbea-224">Wenn eine [Yield](yield-statement.md) -Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4cbea-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="4cbea-225">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="4cbea-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="4cbea-226">Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste](for-each-next-statement.md) Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4cbea-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="4cbea-227">Der Rückgabetyp einer Funktion Iterator möglich <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="4cbea-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="4cbea-228">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="4cbea-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="4cbea-229">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cbea-229">Example</span></span>

<span data-ttu-id="4cbea-230">Im folgenden Beispiel wird die `Function` -Anweisung zum Deklarieren der Name, Parameter und Code, der den Text der form einer `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="4cbea-231">Die `ParamArray` -Modifizierer kann die Funktion, die eine Variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4cbea-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="4cbea-232">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cbea-232">Example</span></span>

<span data-ttu-id="4cbea-233">Im folgenden Beispiel wird die Funktion, die im vorherigen Beispiel deklariert.</span><span class="sxs-lookup"><span data-stu-id="4cbea-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="4cbea-234">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4cbea-234">Example</span></span>

<span data-ttu-id="4cbea-235">Im folgenden Beispiel `DelayAsync` ist ein `Async` `Function` , die einen Rückgabetyp hat <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4cbea-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4cbea-236">`DelayAsync` enthält eine `Return` -Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4cbea-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="4cbea-237">Aus diesem Grund der Deklaration der `DelayAsync` muss einen Rückgabetyp von `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="4cbea-238">Da der Rückgabetyp ist `Task(Of Integer)`, die Auswertung der `Await` Ausdruck in `DoSomethingAsync` erzeugt eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="4cbea-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="4cbea-239">Dies wird in dieser Anweisung veranschaulicht: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="4cbea-240">Die `startButton_Click` Verfahren ist ein Beispiel für eine `Async Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4cbea-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="4cbea-241">Da `DoSomethingAsync` ist ein `Async` -Funktion, die Aufgabe für den Aufruf von `DoSomethingAsync` muss gewartet werden, wie die folgende Anweisung veranschaulicht: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="4cbea-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="4cbea-242">Die `startButton_Click` `Sub` Prozedur muss definiert werden, mit der `Async` Modifizierer, da sie verfügt über eine `Await` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4cbea-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4cbea-243">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cbea-243">See also</span></span>

- [<span data-ttu-id="4cbea-244">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4cbea-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="4cbea-245">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4cbea-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="4cbea-246">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="4cbea-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="4cbea-247">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4cbea-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="4cbea-248">Call-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4cbea-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="4cbea-249">Of</span><span class="sxs-lookup"><span data-stu-id="4cbea-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="4cbea-250">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="4cbea-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="4cbea-251">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="4cbea-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="4cbea-252">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4cbea-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="4cbea-253">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4cbea-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="4cbea-254">Function Expression</span><span class="sxs-lookup"><span data-stu-id="4cbea-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
