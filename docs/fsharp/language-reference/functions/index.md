---
title: Funktionen
description: Informationen Sie zu Funktionen in F# und wie F# gemeinsamen Konstrukte der funktionalen Programmierung unterstützt.
ms.date: 05/16/2016
ms.openlocfilehash: 6e9ef916388745d2dd6874295d06dca656971b3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996787"
---
# <a name="functions"></a><span data-ttu-id="7ef87-103">Funktionen</span><span class="sxs-lookup"><span data-stu-id="7ef87-103">Functions</span></span>

<span data-ttu-id="7ef87-104">Funktionen sind die grundlegende Einheit für die Ausführung des Programms in einer beliebigen Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="7ef87-104">Functions are the fundamental unit of program execution in any programming language.</span></span> <span data-ttu-id="7ef87-105">So wie in anderen Sprachen auch, verfügt eine F#-Funktion über einen Namen, kann Parameter besitzen und Argumente verwenden und verfügt über Text.</span><span class="sxs-lookup"><span data-stu-id="7ef87-105">As in other languages, an F# function has a name, can have parameters and take arguments, and has a body.</span></span> <span data-ttu-id="7ef87-106">F# unterstützt auch funktionale Konstrukte der Programmierung, z.B. das Behandeln von Funktionen als Werte, Verwenden von unbenannten Funktionen als Ausdrücke, die Zusammensetzung von Funktionen zum Bilden neuer Funktionen, Funktionen mit Currying sowie die implizite Definition von Funktionen mit der teilweise Anwendung von Funktionsargumenten.</span><span class="sxs-lookup"><span data-stu-id="7ef87-106">F# also supports functional programming constructs such as treating functions as values, using unnamed functions in expressions, composition of functions to form new functions, curried functions, and the implicit definition of functions by way of the partial application of function arguments.</span></span>

<span data-ttu-id="7ef87-107">Sie definieren Funktionen durch Verwendung des Schlüsselworts `let` oder – sofern die Funktion rekursiv ist – die Schlüsselwortkombination `let rec`.</span><span class="sxs-lookup"><span data-stu-id="7ef87-107">You define functions by using the `let` keyword, or, if the function is recursive, the `let rec` keyword combination.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ef87-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ef87-108">Syntax</span></span>

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a><span data-ttu-id="7ef87-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ef87-109">Remarks</span></span>

<span data-ttu-id="7ef87-110">Der *function-name* ist ein Bezeichner, der die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-110">The *function-name* is an identifier that represents the function.</span></span> <span data-ttu-id="7ef87-111">Der Bezeichner *parameter-list* besteht aus aufeinanderfolgenden Parametern, die durch Leerzeichen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="7ef87-111">The *parameter-list* consists of successive parameters that are separated by spaces.</span></span> <span data-ttu-id="7ef87-112">Sie können einen expliziten Typ für jeden Parameter angeben, wie im Abschnitt „Parameter“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ef87-112">You can specify an explicit type for each parameter, as described in the Parameters section.</span></span> <span data-ttu-id="7ef87-113">Wenn Sie keinen bestimmten Argumenttyp angeben, versucht der Compiler den Typ aus dem Funktionsrumpf abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="7ef87-113">If you do not specify a specific argument type, the compiler attempts to infer the type from the function body.</span></span> <span data-ttu-id="7ef87-114">*function-body* besteht aus einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7ef87-114">The *function-body* consists of an expression.</span></span> <span data-ttu-id="7ef87-115">Der Ausdruck, der den Funktionsrumpf bildet, ist in der Regel ein zusammengesetzter Ausdruck, bestehend aus einer Reihe von Ausdrücken, die in einem abschließenden Ausdruck enden, was der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="7ef87-115">The expression that makes up the function body is typically a compound expression consisting of a number of expressions that culminate in a final expression that is the return value.</span></span> <span data-ttu-id="7ef87-116">Der *return-type* ist ein Doppelpunkt, dem ein Typ folgt und der optional ist.</span><span class="sxs-lookup"><span data-stu-id="7ef87-116">The *return-type* is a colon followed by a type and is optional.</span></span> <span data-ttu-id="7ef87-117">Wenn Sie den Typ des Rückgabewerts nicht explizit angeben, bestimmt der Compiler den Rückgabetyp anhand des abschließenden Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="7ef87-117">If you do not specify the type of the return value explicitly, the compiler determines the return type from the final expression.</span></span>

<span data-ttu-id="7ef87-118">Eine einfache Funktionsdefinition lautet ungefähr folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="7ef87-118">A simple function definition resembles the following:</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="7ef87-119">Im vorherigen Beispiel ist der Funktionsname ist `f`, das Argument `x`, das den Typ `int` verweist, der Funktionsrumpf ist `x + 1`, und der Rückgabewert ist vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="7ef87-119">In the previous example, the function name is `f`, the argument is `x`, which has type `int`, the function body is `x + 1`, and the return value is of type `int`.</span></span>

<span data-ttu-id="7ef87-120">Funktionen können als `inline` markiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-120">Functions can be marked `inline`.</span></span> <span data-ttu-id="7ef87-121">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7ef87-121">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

## <a name="scope"></a><span data-ttu-id="7ef87-122">Bereich</span><span class="sxs-lookup"><span data-stu-id="7ef87-122">Scope</span></span>

<span data-ttu-id="7ef87-123">Auf jeder Ebene des Bereichs, der nicht der Modulbereich ist, ist es kein Fehler, einen Wert oder einen Namen einer Funktion Namen erneut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-123">At any level of scope other than module scope, it is not an error to reuse a value or function name.</span></span> <span data-ttu-id="7ef87-124">Wenn Sie einen Namen wiederverwenden, führt der später deklarierte Name zum Shadowing des früher deklarierten Namens.</span><span class="sxs-lookup"><span data-stu-id="7ef87-124">If you reuse a name, the name declared later shadows the name declared earlier.</span></span> <span data-ttu-id="7ef87-125">Im Bereich der obersten Ebene in einem Modul, müssen Namen jedoch eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7ef87-125">However, at the top level scope in a module, names must be unique.</span></span> <span data-ttu-id="7ef87-126">Der folgende Code generiert z.B. einen Fehler, wenn er im Modulbereich erscheint, jedoch nicht, wenn er innerhalb einer Funktion angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="7ef87-126">For example, the following code produces an error when it appears at module scope, but not when it appears inside a function:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

<span data-ttu-id="7ef87-127">Der folgende Code ist jedoch auf jeder Ebene des Bereichs akzeptabel:</span><span class="sxs-lookup"><span data-stu-id="7ef87-127">But the following code is acceptable at any level of scope:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a><span data-ttu-id="7ef87-128">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ef87-128">Parameters</span></span>

<span data-ttu-id="7ef87-129">Namen von Parametern werden nach dem Funktionsnamen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-129">Names of parameters are listed after the function name.</span></span> <span data-ttu-id="7ef87-130">Sie können einen Typ für einen Parameter angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7ef87-130">You can specify a type for a parameter, as shown in the following example:</span></span>

```fsharp
let f (x : int) = x + 1
```

<span data-ttu-id="7ef87-131">Wenn Sie einen Typ angeben, folgt er auf den Namen des Parameters und wird durch einen Doppelpunkt von diesem getrennt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-131">If you specify a type, it follows the name of the parameter and is separated from the name by a colon.</span></span> <span data-ttu-id="7ef87-132">Wenn Sie den Typ für den Parameter weglassen, wird der Parametertyp vom Compiler abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7ef87-132">If you omit the type for the parameter, the parameter type is inferred by the compiler.</span></span> <span data-ttu-id="7ef87-133">In der folgenden Funktion wird z.B. das Argument `x` vom Typ `int` abgeleitet, da 1 vom Typ `int` ist.</span><span class="sxs-lookup"><span data-stu-id="7ef87-133">For example, in the following function definition, the argument `x` is inferred to be of type `int` because 1 is of type `int`.</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="7ef87-134">Allerdings versucht der Compiler die Funktion so allgemein wie möglich zu machen.</span><span class="sxs-lookup"><span data-stu-id="7ef87-134">However, the compiler will attempt to make the function as generic as possible.</span></span> <span data-ttu-id="7ef87-135">Beachten Sie beispielsweise folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7ef87-135">For example, note the following code:</span></span>

```fsharp
let f x = (x, x)
```

<span data-ttu-id="7ef87-136">Die Funktion erstellt ein Tupel aus einem Argument eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="7ef87-136">The function creates a tuple from one argument of any type.</span></span> <span data-ttu-id="7ef87-137">Da der Typ nicht angegeben ist, kann die Funktion mit jedem Argumenttyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-137">Because the type is not specified, the function can be used with any argument type.</span></span> <span data-ttu-id="7ef87-138">Weitere Informationen finden Sie unter [Automatische Verallgemeinerung](../generics/automatic-generalization.md).</span><span class="sxs-lookup"><span data-stu-id="7ef87-138">For more information, see [Automatic Generalization](../generics/automatic-generalization.md).</span></span>

## <a name="function-bodies"></a><span data-ttu-id="7ef87-139">Funktionsrümpfe</span><span class="sxs-lookup"><span data-stu-id="7ef87-139">Function Bodies</span></span>

<span data-ttu-id="7ef87-140">Ein Funktionsrumpf kann Definitionen von lokalen Variablen und Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ef87-140">A function body can contain definitions of local variables and functions.</span></span> <span data-ttu-id="7ef87-141">Diese Variablen und Funktionen sind im Bereich des Texts der aktuellen Funktion enthalten, jedoch nicht außerhalb.</span><span class="sxs-lookup"><span data-stu-id="7ef87-141">Such variables and functions are in scope in the body of the current function but not outside it.</span></span> <span data-ttu-id="7ef87-142">Wenn Sie die einfache Syntaxoption aktiviert haben, müssen Sie einen Einzug verwenden, um anzugeben, dass sich eine Definition in einem Funktionsrumpf befindet, so wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-142">When you have the lightweight syntax option enabled, you must use indentation to indicate that a definition is in a function body, as shown in the following example:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

<span data-ttu-id="7ef87-143">Weitere Informationen finden Sie unter [Richtlinien für das Formatieren von Code](../code-formatting-guidelines.md) und [Ausführliche Syntax](../verbose-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="7ef87-143">For more information, see [Code Formatting Guidelines](../code-formatting-guidelines.md) and [Verbose Syntax](../verbose-syntax.md).</span></span>

## <a name="return-values"></a><span data-ttu-id="7ef87-144">Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="7ef87-144">Return Values</span></span>

<span data-ttu-id="7ef87-145">Der Compiler verwendet den letzten Ausdruck in einem Funktionsrumpf, um den Rückgabewert und den Typ zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7ef87-145">The compiler uses the final expression in a function body to determine the return value and type.</span></span> <span data-ttu-id="7ef87-146">Der Compiler kann den Typ des abschließenden Ausdrucks möglicherweise von vorherigen Ausdrücken ableiten.</span><span class="sxs-lookup"><span data-stu-id="7ef87-146">The compiler might infer the type of the final expression from previous expressions.</span></span> <span data-ttu-id="7ef87-147">In der Funktion `cylinderVolume`, die im vorherigen Abschnitt gezeigt wird, wird bestimmt, dass der Typ `pi` vom Typ des Literals `3.14159` `float` ist.</span><span class="sxs-lookup"><span data-stu-id="7ef87-147">In the function `cylinderVolume`, shown in the previous section, the type of `pi` is determined from the type of the literal `3.14159` to be `float`.</span></span> <span data-ttu-id="7ef87-148">Der Compiler verwendet den Typ `pi`, um zu bestimmen, dass der Typ des Ausdrucks `h * pi * r * r` `float` ist.</span><span class="sxs-lookup"><span data-stu-id="7ef87-148">The compiler uses the type of `pi` to determine the type of the expression `h * pi * r * r` to be `float`.</span></span> <span data-ttu-id="7ef87-149">Daher ist der allgemeine Rückgabetyp der Funktion `float`.</span><span class="sxs-lookup"><span data-stu-id="7ef87-149">Therefore, the overall return type of the function is `float`.</span></span>

<span data-ttu-id="7ef87-150">Um den Rückgabewert explizit anzugeben, schreiben Sie den Code wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7ef87-150">To specify the return value explicitly, write the code as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

<span data-ttu-id="7ef87-151">Wie der oben geschriebene Code, wendet der Compiler **float** auf gesamten Funktion an; wenn Sie sie auch auf Parametertypen anwenden möchten, verwenden Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7ef87-151">As the code is written above, the compiler applies **float** to the entire function; if you mean to apply it to the parameter types as well, use the following code:</span></span>

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a><span data-ttu-id="7ef87-152">Aufrufen einer Funktion</span><span class="sxs-lookup"><span data-stu-id="7ef87-152">Calling a Function</span></span>

<span data-ttu-id="7ef87-153">Sie können Funktionen aufrufen, indem den Funktionsnamen, gefolgt von einem Leerzeichen angeben, und dann beliebige Argumente, die durch Leerzeichen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="7ef87-153">You call functions by specifying the function name followed by a space and then any arguments separated by spaces.</span></span> <span data-ttu-id="7ef87-154">Um z.B. die Funktion **cylinderVolume** abzurufen und das Ergebnis dem Wert **vol** zuzuweisen, schreiben Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7ef87-154">For example, to call the function **cylinderVolume** and assign the result to the value **vol**, you write the following code:</span></span>

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a><span data-ttu-id="7ef87-155">Teilweise Anwendung von Argumenten</span><span class="sxs-lookup"><span data-stu-id="7ef87-155">Partial Application of Arguments</span></span>

<span data-ttu-id="7ef87-156">Wenn Sie weniger als die angegebene Anzahl von Argumenten angeben, erstellen Sie eine neue Funktion, die die übrigen Argumente erwartet.</span><span class="sxs-lookup"><span data-stu-id="7ef87-156">If you supply fewer than the specified number of arguments, you create a new function that expects the remaining arguments.</span></span> <span data-ttu-id="7ef87-157">Diese Methode zum Behandeln von Argumenten  wird als *Currying* bezeichnet und ist ein Merkmal funktionaler Programmiersprachen wie F#.</span><span class="sxs-lookup"><span data-stu-id="7ef87-157">This method of handling arguments is referred to as *currying* and is a characteristic of functional programming languages like F#.</span></span> <span data-ttu-id="7ef87-158">Nehmen wir beispielsweise an, dass Sie mit zwei Pipegrößen arbeiten: eine besitzt den Radius von **2,0** und die andere einen Radius von **3,0**.</span><span class="sxs-lookup"><span data-stu-id="7ef87-158">For example, suppose you are working with two sizes of pipe: one has a radius of **2.0** and the other has a radius of **3.0**.</span></span> <span data-ttu-id="7ef87-159">Sie können Funktionen erstellen, die die Menge der Pipe wie folgt bestimmen:</span><span class="sxs-lookup"><span data-stu-id="7ef87-159">You could create functions that determine the volume of pipe as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

<span data-ttu-id="7ef87-160">Sie geben dann das zusätzliche Argument an, das für unterschiedliche Längen der Pipe mit den zwei verschiedenen Größen benötigt wird:</span><span class="sxs-lookup"><span data-stu-id="7ef87-160">You would then supply the additional argument as needed for various lengths of pipe of the two different sizes:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a><span data-ttu-id="7ef87-161">Rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="7ef87-161">Recursive Functions</span></span>

<span data-ttu-id="7ef87-162">*Rekursive Funktionen* sind Funktionen, die sich selbst aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7ef87-162">*Recursive functions* are functions that call themselves.</span></span> <span data-ttu-id="7ef87-163">Sie erfordern die Angabe des Schlüsselworts **rec**, das dem Schlüsselwort **let** folgt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-163">They require that you specify the **rec** keyword following the **let** keyword.</span></span> <span data-ttu-id="7ef87-164">Rufen Sie die rekursive Funktion im Rumpf der Funktion so auf, wie Sie auch jede andere Funktion aufrufen würden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-164">Invoke the recursive function from within the body of the function just as you would invoke any function call.</span></span> <span data-ttu-id="7ef87-165">Die folgende rekursive Funktion berechnet den *n*<sup>th</sup> Fibonacci-Zahl.</span><span class="sxs-lookup"><span data-stu-id="7ef87-165">The following recursive function computes the *n*<sup>th</sup> Fibonacci number.</span></span> <span data-ttu-id="7ef87-166">Die die Fibonacci-Zahlenfolge ist seit dem Altertum bekannt und ist eine Sequenz, in der die einzelnen aufeinander folgenden Zahlen die Summe der vorherigen zwei Zahlen in der Sequenz sind.</span><span class="sxs-lookup"><span data-stu-id="7ef87-166">The Fibonacci number sequence has been known since antiquity and is a sequence in which each successive number is the sum of the previous two numbers in the sequence.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

<span data-ttu-id="7ef87-167">Einige rekursive Funktionen können auf einem Programmstapel möglicherweise zum Überlauf führen oder ineffizient ausgeführt werden, wenn Sie sie nicht sorgfältig und unter Beachtung besonderer Methoden schreiben, z.B. mit der Verwendung von Akkumulatoren und Fortsetzungen.</span><span class="sxs-lookup"><span data-stu-id="7ef87-167">Some recursive functions might overflow the program stack or perform inefficiently if you do not write them with care and with awareness of special techniques, such as the use of accumulators and continuations.</span></span>

## <a name="function-values"></a><span data-ttu-id="7ef87-168">Funktionswerte</span><span class="sxs-lookup"><span data-stu-id="7ef87-168">Function Values</span></span>

<span data-ttu-id="7ef87-169">In F# werden alle Funktionen als Werte betrachtet. Sie sind in der Tat als *Funktionswerte* bekannt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-169">In F#, all functions are considered values; in fact, they are known as *function values*.</span></span> <span data-ttu-id="7ef87-170">Da Funktionen Werte sind, können sie als Argumente für andere Funktionen oder in anderen Kontexten verwendet werden, in denen Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-170">Because functions are values, they can be used as arguments to other functions or in other contexts where values are used.</span></span> <span data-ttu-id="7ef87-171">Es folgt ein Beispiel für eine Funktion, die den Wert einer Funktion als Argument akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="7ef87-171">Following is an example of a function that takes a function value as an argument:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

<span data-ttu-id="7ef87-172">Sie geben den Typ eines Funktionswerts mithilfe des `->`-Token an.</span><span class="sxs-lookup"><span data-stu-id="7ef87-172">You specify the type of a function value by using the `->` token.</span></span> <span data-ttu-id="7ef87-173">Auf der linken Seite dieses Tokens befindet sich der Typ des Arguments, und auf der rechten Seite befindet sich der Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="7ef87-173">On the left side of this token is the type of the argument, and on the right side is the return value.</span></span> <span data-ttu-id="7ef87-174">Im vorherigen Beispiel ist `apply1` eine Funktion, die eine `transform`-Funktion als Argument verwendet, wobei `transform` eine Funktion ist, die einen Integer nimmt und einen anderen dafür zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7ef87-174">In the previous example, `apply1` is a function that takes a function `transform` as an argument, where `transform` is a function that takes an integer and returns another integer.</span></span> <span data-ttu-id="7ef87-175">Im folgenden Code wird die Verwendung von `apply1` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7ef87-175">The following code shows how to use `apply1`:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

<span data-ttu-id="7ef87-176">Der Wert von `result` wird nach der Ausführung des vorangehenden Codes 101 sein.</span><span class="sxs-lookup"><span data-stu-id="7ef87-176">The value of `result` will be 101 after the previous code runs.</span></span>

<span data-ttu-id="7ef87-177">Mehrere Argumente werden durch aufeinander folgende `->`-Token getrennt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7ef87-177">Multiple arguments are separated by successive `->` tokens, as shown in the following example:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

<span data-ttu-id="7ef87-178">Das Ergebnis ist 200.</span><span class="sxs-lookup"><span data-stu-id="7ef87-178">The result is 200.</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="7ef87-179">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7ef87-179">Lambda Expressions</span></span>

<span data-ttu-id="7ef87-180">Ein *Lambdaausdruck* ist eine unbenannte Funktion.</span><span class="sxs-lookup"><span data-stu-id="7ef87-180">A *lambda expression* is an unnamed function.</span></span> <span data-ttu-id="7ef87-181">Im vorherigen Beispiel könnten Sie Lambdaausdrücke verwenden, anstatt benannte Funktionen als **increment** und **mul** zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7ef87-181">In the previous examples, instead of defining named functions **increment** and **mul**, you could use lambda expressions as follows:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

<span data-ttu-id="7ef87-182">Sie definieren Lambdaausdrücke mithilfe des `fun`-Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="7ef87-182">You define lambda expressions by using the `fun` keyword.</span></span> <span data-ttu-id="7ef87-183">Ein Lambdaausdruck ähnelt einer Funktionsdefinition, außer dass statt eines `=`-Tokens das `->`-Token zum Trennen der Argumentliste vom Funktionsrumpf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ef87-183">A lambda expression resembles a function definition, except that instead of the `=` token, the `->` token is used to separate the argument list from the function body.</span></span> <span data-ttu-id="7ef87-184">So wie in einer regulären Funktionsdefinition, können Argumenttypen explizit abgeleitet oder angegeben werden. Der Rückgabetyp des Lambdaausdrucks wird vom Typ des letzten Ausdrucks im Text abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7ef87-184">As in a regular function definition, the argument types can be inferred or specified explicitly, and the return type of the lambda expression is inferred from the type of the last expression in the body.</span></span> <span data-ttu-id="7ef87-185">Weitere Informationen finden Sie unter [Lambda-Ausdrücken: Die `fun` Schlüsselwort](../functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="7ef87-185">For more information, see [Lambda Expressions: The `fun` Keyword](../functions/lambda-expressions-the-fun-keyword.md).</span></span>

## <a name="function-composition-and-pipelining"></a><span data-ttu-id="7ef87-186">Funktionskomposition und Pipelining</span><span class="sxs-lookup"><span data-stu-id="7ef87-186">Function Composition and Pipelining</span></span>

<span data-ttu-id="7ef87-187">Funktionen in F# können aus anderen Funktionen zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-187">Functions in F# can be composed from other functions.</span></span> <span data-ttu-id="7ef87-188">Die Zusammensetzung der beiden Funktionen **function1** und **function2** ist eine weitere Funktion, die die Anwendung von **function1** gefolgt von der Anwendung von **function2** darstellt:</span><span class="sxs-lookup"><span data-stu-id="7ef87-188">The composition of two functions **function1** and **function2** is another function that represents the application of **function1** followed the application of **function2**:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

<span data-ttu-id="7ef87-189">Das Ergebnis ist 202.</span><span class="sxs-lookup"><span data-stu-id="7ef87-189">The result is 202.</span></span>

<span data-ttu-id="7ef87-190">Pipelining ermöglicht, dass Funktionsaufrufe miteinander als aufeinanderfolgende Operationen verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="7ef87-190">Pipelining enables function calls to be chained together as successive operations.</span></span> <span data-ttu-id="7ef87-191">Pipelining funktioniert wie Folgt:</span><span class="sxs-lookup"><span data-stu-id="7ef87-191">Pipelining works as follows:</span></span>

```fsharp
let result = 100 |> function1 |> function2
```

<span data-ttu-id="7ef87-192">Das Ergebnis ist wieder 202.</span><span class="sxs-lookup"><span data-stu-id="7ef87-192">The result is again 202.</span></span>

<span data-ttu-id="7ef87-193">Die Kompositionsoperatoren nehmen zwei Funktionen und geben eine Funktion zurück. Dagegen nehmen Pipeline-Operatoren eine Funktion und ein Argument und geben einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="7ef87-193">The composition operators take two functions and return a function; by contrast, the pipeline operators take a function and an argument and return a value.</span></span> <span data-ttu-id="7ef87-194">Das folgende Codebeispiel zeigt den Unterschied zwischen den Pipeline- und Kompositionsoperatoren durch Darstellung der Unterschiede in den Funktionssignaturen und in der Nutzung.</span><span class="sxs-lookup"><span data-stu-id="7ef87-194">The following code example shows the difference between the pipeline and composition operators by showing the differences in the function signatures and usage.</span></span>

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a><span data-ttu-id="7ef87-195">Überladen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="7ef87-195">Overloading Functions</span></span>

<span data-ttu-id="7ef87-196">Sie können die Methoden eines Typs überladen, jedoch keine Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7ef87-196">You can overload methods of a type but not functions.</span></span> <span data-ttu-id="7ef87-197">Weitere Informationen finden Sie unter [Methoden](../members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="7ef87-197">For more information, see [Methods](../members/methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ef87-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ef87-198">See also</span></span>

- [<span data-ttu-id="7ef87-199">Werte</span><span class="sxs-lookup"><span data-stu-id="7ef87-199">Values</span></span>](../values/index.md)
- [<span data-ttu-id="7ef87-200">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7ef87-200">F# Language Reference</span></span>](../index.md)