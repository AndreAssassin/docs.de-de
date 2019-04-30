---
title: While...End While-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934224"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="0de57-102">While...End While-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0de57-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="0de57-103">Führt eine Reihe von Anweisungen aus, solange eine angegebene Bedingung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0de57-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0de57-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="0de57-105">Teile</span><span class="sxs-lookup"><span data-stu-id="0de57-105">Parts</span></span>  
  
|<span data-ttu-id="0de57-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0de57-106">Term</span></span>|<span data-ttu-id="0de57-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0de57-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="0de57-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0de57-108">Required.</span></span> <span data-ttu-id="0de57-109">`Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0de57-109">`Boolean` expression.</span></span> <span data-ttu-id="0de57-110">Wenn `condition` ist `Nothing`, Visual Basic behandelt es als `False`.</span><span class="sxs-lookup"><span data-stu-id="0de57-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="0de57-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0de57-111">Optional.</span></span> <span data-ttu-id="0de57-112">Eine oder mehrere Anweisungen nach `While`, die jedes Mal ausführen `condition` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0de57-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="0de57-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0de57-113">Optional.</span></span> <span data-ttu-id="0de57-114">Überträgt die Steuerung an die nächste Iteration der `While` Block.</span><span class="sxs-lookup"><span data-stu-id="0de57-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="0de57-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0de57-115">Optional.</span></span> <span data-ttu-id="0de57-116">Überträgt die Steuerung von der `While` Block.</span><span class="sxs-lookup"><span data-stu-id="0de57-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="0de57-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0de57-117">Required.</span></span> <span data-ttu-id="0de57-118">Beendet die Definition des `While`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="0de57-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0de57-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0de57-119">Remarks</span></span>  
 <span data-ttu-id="0de57-120">Verwenden einer `While...End While` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl an, wie oft wiederholen möchten, solange eine Bedingung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0de57-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="0de57-121">Wenn Sie möchten mehr Flexibilität bezüglich der, in dem die Bedingung getestet, und welches Ergebnis testen, ob es, empfiehlt sich möglicherweise die [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0de57-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="0de57-122">Wenn Sie den Anweisungen über eine festgelegte Anzahl von Fällen wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="0de57-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0de57-123">Die `While` -Schlüsselwort wird auch verwendet, der [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0de57-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="0de57-124">Wenn `condition` ist `True`, werden alle von der `statements` ausgeführt, bis die `End While` -Anweisung gefunden.</span><span class="sxs-lookup"><span data-stu-id="0de57-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="0de57-125">Anschließend zurück zum Steuern der `While` -Anweisung und `condition` erneut aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0de57-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="0de57-126">Wenn `condition` ist immer noch `True`, wird der Prozess wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0de57-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="0de57-127">Es verfügt `False`, wird für die die folgende Anweisung die Steuerung der `End While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0de57-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="0de57-128">Die `While` Anweisung immer überprüft die Bedingung aus, bevor die Schleife gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0de57-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="0de57-129">Die Schleife wird ausgeführt, solange die Bedingung bleibt `True`.</span><span class="sxs-lookup"><span data-stu-id="0de57-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="0de57-130">Wenn `condition` ist `False` bei der Eingabe von der schleifenstatus nicht ausgeführt noch einmal.</span><span class="sxs-lookup"><span data-stu-id="0de57-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="0de57-131">Die `condition` Ergebnisse von einem Vergleich von zwei Werten, aber es können in der Regel ein Ausdruck, der ausgewertet wird werden eine [Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`).</span><span class="sxs-lookup"><span data-stu-id="0de57-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="0de57-132">Dieser Ausdruck kann einen Wert mit einem anderen Datentyp, z. B. eines numerischen Typs, der in konvertiert wurde enthalten `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0de57-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="0de57-133">Sie können schachteln `While` Schleifen, indem Sie eine Schleife in einem anderen platzieren.</span><span class="sxs-lookup"><span data-stu-id="0de57-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="0de57-134">Sie können auch verschiedene Arten von Steuerungsstrukturen in anderen schachteln.</span><span class="sxs-lookup"><span data-stu-id="0de57-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="0de57-135">Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="0de57-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="0de57-136">Beenden und</span><span class="sxs-lookup"><span data-stu-id="0de57-136">Exit While</span></span>  
 <span data-ttu-id="0de57-137">Die [zu beenden, während](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung bieten eine weitere Möglichkeit zum Beenden einer `While` Schleife.</span><span class="sxs-lookup"><span data-stu-id="0de57-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="0de57-138">`Exit While` überträgt die Steuerung sofort an die die folgende Anweisung die `End While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0de57-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="0de57-139">In der Regel `Exit While` nach eine Bedingung ausgewertet wird (z. B. in einer `If...Then...Else` Struktur).</span><span class="sxs-lookup"><span data-stu-id="0de57-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="0de57-140">Sie möchten eine Schleife zu beenden, wenn Sie eine Bedingung, die es nicht erforderlich oder unmöglich ist erkennen, um den Vorgang fortzusetzen, Iteration, z. B. einen falschen Wert oder eine Anforderung zum Beenden ist.</span><span class="sxs-lookup"><span data-stu-id="0de57-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="0de57-141">Können Sie `Exit While` beim Testen für eine Bedingung, die dazu führen könnte, dass ein *Endlosschleife*, d.h. eine Schleife, die eine sehr große oder sogar unendliche Anzahl von Malen ausgeführt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="0de57-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="0de57-142">Anschließend können Sie `Exit While` die Schleife mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="0de57-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="0de57-143">Sie können eine beliebige Anzahl von platzieren `Exit While` Anweisungen, die an einer beliebigen Stelle in der `While` Schleife.</span><span class="sxs-lookup"><span data-stu-id="0de57-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="0de57-144">Bei der Verwendung in geschachtelten `While` Schleifen `Exit While` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene Schachtelungsebenen.</span><span class="sxs-lookup"><span data-stu-id="0de57-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="0de57-145">Die `Continue While` -Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife.</span><span class="sxs-lookup"><span data-stu-id="0de57-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="0de57-146">Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0de57-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de57-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0de57-147">Example</span></span>  
 <span data-ttu-id="0de57-148">Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable ist größer als 10.</span><span class="sxs-lookup"><span data-stu-id="0de57-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="0de57-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0de57-149">Example</span></span>  
 <span data-ttu-id="0de57-150">Das folgende Beispiel veranschaulicht die Verwendung der `Continue While` und `Exit While` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="0de57-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="0de57-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0de57-151">Example</span></span>  
 <span data-ttu-id="0de57-152">Das folgende Beispiel liest alle Zeilen in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="0de57-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="0de57-153">Die <xref:System.IO.File.OpenText%2A> Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0de57-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="0de57-154">In der `While` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode der `StreamReader` bestimmt, ob die Datei mit zusätzliche Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="0de57-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="0de57-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0de57-155">See also</span></span>

- [<span data-ttu-id="0de57-156">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="0de57-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="0de57-157">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0de57-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="0de57-158">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0de57-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0de57-159">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0de57-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="0de57-160">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0de57-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="0de57-161">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0de57-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="0de57-162">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0de57-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
