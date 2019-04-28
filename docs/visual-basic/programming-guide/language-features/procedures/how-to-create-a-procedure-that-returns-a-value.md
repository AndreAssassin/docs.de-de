---
title: 'Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 115c1df4bd49d5848d72c4cbd0242a49a12740c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863726"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e7170-102">Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7170-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="e7170-103">Sie verwenden eine `Function` -Prozedur, einen Wert an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7170-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="e7170-104">Zum Erstellen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7170-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="e7170-105">Verwendung außerhalb anderer Prozeduren ein `Function` -Anweisung, gefolgt von einer `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e7170-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="e7170-106">In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann die Liste der Parameter in Klammern.</span><span class="sxs-lookup"><span data-stu-id="e7170-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="e7170-107">Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des zurückgegebenen Werts angeben.</span><span class="sxs-lookup"><span data-stu-id="e7170-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="e7170-108">Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e7170-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="e7170-109">Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7170-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="e7170-110">Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="e7170-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="e7170-111">Das folgende Beispiel zeigt einen typischen Aufruf von `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="e7170-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e7170-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7170-112">See also</span></span>

- [<span data-ttu-id="e7170-113">Verfahren</span><span class="sxs-lookup"><span data-stu-id="e7170-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e7170-114">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e7170-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e7170-115">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="e7170-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e7170-116">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="e7170-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e7170-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e7170-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e7170-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e7170-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e7170-119">Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="e7170-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="e7170-120">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7170-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
