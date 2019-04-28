---
title: 'Vorgehensweise: Übergeben von Argumenten an eine Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863440"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="86e77-102">Vorgehensweise: Übergeben von Argumenten an eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86e77-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="86e77-103">Wenn Sie eine Prozedur aufrufen, verwenden Sie den Namen der Prozedur mit einer Argumentliste in Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="86e77-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="86e77-104">Sie geben Sie ein Argument für alle erforderlichen Parameter, die die Prozedur definiert, und geben Sie optional die Argumente, die `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="86e77-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="86e77-105">Wenn Sie keinen angeben einer `Optional` Parameter im Aufruf, müssen Sie ein Komma, um seine Position in der Argumentliste zu markieren, wenn Sie alle nachfolgenden Argumente angeben einschließen.</span><span class="sxs-lookup"><span data-stu-id="86e77-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="86e77-106">Wenn Sie beabsichtigen, ein Argument eines Datentyps unterscheidet, von der entsprechenden Parameter, wie z. B. übergeben werden `Byte` zu `String`, Sie können festlegen, dass den Switch-typüberprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) zu `Off`.</span><span class="sxs-lookup"><span data-stu-id="86e77-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="86e77-107">Wenn `Option Strict` ist `On`, verwenden Sie entweder erweiternde Konvertierungen oder explizite Konvertierungsschlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="86e77-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="86e77-108">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="86e77-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="86e77-109">Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="86e77-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="86e77-110">Um ein oder mehrere Argumente an eine Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="86e77-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="86e77-111">Führen Sie den Namen der Prozedur mit Klammern, in der aufrufenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="86e77-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="86e77-112">Fügen Sie in den Klammern einer Argumentliste aus.</span><span class="sxs-lookup"><span data-stu-id="86e77-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="86e77-113">Fügen Sie ein Argument für die einzelnen erforderlichen Parameter an, dass die Prozedur definiert, und trennen Sie die Argumente durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="86e77-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="86e77-114">Stellen Sie sicher, dass jedes Argument ist, dass ein gültiger Ausdruck, der einen Daten-Typ konvertierbar sein in den Typ der Prozedur ergibt für den entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="86e77-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="86e77-115">Wenn ein Parameter, als definiert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), Sie können in der Argumentliste einfügen oder ihn auslassen.</span><span class="sxs-lookup"><span data-stu-id="86e77-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="86e77-116">Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert ein.</span><span class="sxs-lookup"><span data-stu-id="86e77-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="86e77-117">Wenn Sie weglassen, dass ein Argument für eine `Optional` Parameter ist ein weiterer Parameter nach ihm in der Parameterliste, Sie können den Platz von das ausgelassene Argument markieren, indem ein zusätzliches Komma in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="86e77-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="86e77-118">Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktion.</span><span class="sxs-lookup"><span data-stu-id="86e77-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="86e77-119">Im vorherige Beispiel stellt das erforderliche erste-Argument, das wird von die Meldungszeichenfolge, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86e77-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="86e77-120">Sie lässt es sich um ein Argument für den optionalen zweiten Parameter, der angibt, die Schaltflächen im Meldungsfeld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86e77-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="86e77-121">Da der Aufruf einen Wert nicht angegeben wird `MsgBox` verwendet den Standardwert `MsgBoxStyle.OKOnly`, wird angezeigt, die nur eine **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="86e77-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="86e77-122">Das zweite Komma in der Argumentliste markiert die Stelle des zweiten Arguments nicht angegeben, und die letzte Zeichenfolge übergeben wird, auf dem dritten optionalen Parameter der `MsgBox`, d.h., dass der Text, der in der Titelleiste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="86e77-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e77-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86e77-123">See also</span></span>

- [<span data-ttu-id="86e77-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="86e77-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="86e77-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="86e77-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="86e77-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="86e77-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="86e77-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="86e77-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="86e77-128">Vorgehensweise: Definieren eines Parameters für eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="86e77-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="86e77-129">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="86e77-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="86e77-130">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="86e77-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="86e77-131">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="86e77-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="86e77-132">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="86e77-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="86e77-133">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86e77-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
