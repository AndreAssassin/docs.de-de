---
title: Gelockerte Delegatenkonvertierung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842719"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="f75f7-102">Gelockerte Delegatenkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f75f7-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="f75f7-103">Gelockerte delegatenkonvertierung können Sie Subs und Funktionen Delegaten oder Handlern zugewiesen werden, auch wenn deren Signaturen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f75f7-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="f75f7-104">Aus diesem Grund ist die Bindung an Delegaten konsistent mit der Bindung, die bereits für Methodenaufrufe zulässig.</span><span class="sxs-lookup"><span data-stu-id="f75f7-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="f75f7-105">Parameter und Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="f75f7-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="f75f7-106">Anstelle der Signatur der genaue Übereinstimmung, gelockerte Konvertierung erfordert, dass die folgenden Bedingungen erfüllt sein, wenn `Option Strict` nastaven NA hodnotu `On`:</span><span class="sxs-lookup"><span data-stu-id="f75f7-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="f75f7-107">Eine erweiternde Konvertierung muss vorhanden sein, über den Datentyp jedes einzelnen Delegatparameters in den Datentyp des entsprechenden Parameters der Funktion zugewiesen oder `Sub`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="f75f7-108">Im folgenden Beispiel ist der Delegat `Del1` verfügt über einen Parameter einer `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="f75f7-109">Parameter `m` Ausdrücke müssen in der zugewiesenen Lambda-Ausdruck einen Datentyp, der für das eine erweiternde Konvertierung vorhanden ist `Integer`, z. B. `Long` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="f75f7-110">Einschränkende Konvertierungen sind zulässig, nur, wenn `Option Strict` nastaven NA hodnotu `Off`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
-   <span data-ttu-id="f75f7-111">Eine erweiternde Konvertierung muss vorhanden sein, in die entgegengesetzte Richtung aus dem Rückgabetyp der Funktion zugewiesen oder `Sub` in den Rückgabetyp des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="f75f7-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="f75f7-112">In den folgenden Beispielen muss der Text der einzelnen zugewiesenen Lambda-Ausdrücke ausgewertet werden in einen Datentyp, der auf erweitert wird `Integer` , da der Rückgabetyp der `del1` ist `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="f75f7-113">Wenn `Option Strict` nastaven NA hodnotu `Off`, wird die Einschränkung erweiternde in beide Richtungen entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="f75f7-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="f75f7-114">Parameterangaben auslassen</span><span class="sxs-lookup"><span data-stu-id="f75f7-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="f75f7-115">Lockere Delegaten ermöglichen außerdem vollständig Parameterangaben in der zugewiesenen Methode weglassen:</span><span class="sxs-lookup"><span data-stu-id="f75f7-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="f75f7-116">Beachten Sie, dass Sie nicht einige Parameter angeben und anderen weglassen.</span><span class="sxs-lookup"><span data-stu-id="f75f7-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="f75f7-117">Die Möglichkeit, Parameter auslassen, empfiehlt sich in einer Situation wie die Definition eines ereignishandlers, in denen mehrere komplexe Parameter beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="f75f7-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="f75f7-118">Die Argumente für einige Ereignishandler werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f75f7-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="f75f7-119">Stattdessen greift der Handler direkt über den Zustand des Steuerelements auf dem das Ereignis registriert ist, und die Argumente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f75f7-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="f75f7-120">Lockere Delegaten können Sie die Argumente in der diese Deklarationen, wenn keine Mehrdeutigkeiten auftreten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="f75f7-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="f75f7-121">Im folgenden Beispiel, die vollständig angegebene Methode `OnClick` kann wie folgt umgeschrieben werden `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="f75f7-122">AddressOf-Beispiele</span><span class="sxs-lookup"><span data-stu-id="f75f7-122">AddressOf Examples</span></span>  
 <span data-ttu-id="f75f7-123">Lambda-Ausdrücke werden in den vorherigen Beispielen verwendet, um die typbeziehungen vereinfachen finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="f75f7-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="f75f7-124">Die lockerungen für die gleiche dürfen jedoch auf Zuweisungen von Delegaten, mit denen `AddressOf`, `Handles`, oder `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="f75f7-125">Im folgenden Beispiel zu Funktionen `f1`, `f2`, `f3`, und `f4` können alle zugewiesen werden `Del1`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="f75f7-126">Das folgende Beispiel ist nur gültig, wenn `Option Strict` nastaven NA hodnotu `Off`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="f75f7-127">Löschen die Funktion zurück</span><span class="sxs-lookup"><span data-stu-id="f75f7-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="f75f7-128">Gelockerte delegatenkonvertierung können Sie eine Funktion zum Zuweisen einer `Sub` Delegaten effektiv ignoriert den Rückgabewert der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f75f7-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="f75f7-129">Allerdings kann nicht zugewiesen werden eine `Sub` auf eine zu delegierende Funktion.</span><span class="sxs-lookup"><span data-stu-id="f75f7-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="f75f7-130">Im folgenden Beispiel ist die Adresse der Funktion `doubler` zugewiesen `Sub` Delegieren `Del3`.</span><span class="sxs-lookup"><span data-stu-id="f75f7-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f75f7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f75f7-131">See also</span></span>

- [<span data-ttu-id="f75f7-132">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f75f7-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="f75f7-133">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f75f7-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="f75f7-134">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f75f7-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f75f7-135">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f75f7-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f75f7-136">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="f75f7-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f75f7-137">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f75f7-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
