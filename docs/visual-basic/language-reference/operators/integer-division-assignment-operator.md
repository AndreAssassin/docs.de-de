---
title: '\= -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842537"
---
# <a name="-operator"></a><span data-ttu-id="8c128-102">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="8c128-102">\\= Operator</span></span>
<span data-ttu-id="8c128-103">Dividiert den Wert einer Variablen oder Eigenschaft den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8c128-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c128-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c128-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8c128-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8c128-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="8c128-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c128-106">Required.</span></span> <span data-ttu-id="8c128-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8c128-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="8c128-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c128-108">Required.</span></span> <span data-ttu-id="8c128-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8c128-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c128-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c128-110">Remarks</span></span>  
 <span data-ttu-id="8c128-111">Das Element auf der linken Seite von der `\=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="8c128-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="8c128-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="8c128-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="8c128-113">Die `\=` Operator dividiert den Wert einer Variablen oder Eigenschaft auf der linken Seite durch den Wert auf der rechten Seite, und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft auf der linken Seite</span><span class="sxs-lookup"><span data-stu-id="8c128-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="8c128-114">Weitere Informationen zu ganzzahligen Division, finden Sie unter [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8c128-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8c128-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="8c128-115">Overloading</span></span>  
 <span data-ttu-id="8c128-116">Die `\` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="8c128-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8c128-117">Das Überladen der `\` Operator beeinflusst das Verhalten von der `\=` Operator.</span><span class="sxs-lookup"><span data-stu-id="8c128-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="8c128-118">Wenn Ihr Code verwendet `\=` für eine Klasse oder Struktur, die Überladungen `\`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="8c128-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8c128-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8c128-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c128-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c128-120">Example</span></span>  
 <span data-ttu-id="8c128-121">Im folgenden Beispiel wird die `\=` Operator, um eine teilen `Integer` Variable, indem Sie das zweite und das ganzzahlige Ergebnis der ersten Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8c128-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="8c128-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c128-122">See also</span></span>

- [<span data-ttu-id="8c128-123">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c128-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="8c128-124">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c128-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="8c128-125">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8c128-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="8c128-126">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="8c128-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="8c128-127">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c128-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8c128-128">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8c128-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8c128-129">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8c128-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
