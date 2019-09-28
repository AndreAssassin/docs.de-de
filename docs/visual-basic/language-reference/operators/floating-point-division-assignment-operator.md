---
title: /=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592173"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="6753f-102">/=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6753f-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="6753f-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Gleit Komma Ergebnis der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="6753f-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6753f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6753f-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6753f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6753f-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="6753f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6753f-106">Required.</span></span> <span data-ttu-id="6753f-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6753f-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="6753f-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6753f-108">Required.</span></span> <span data-ttu-id="6753f-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6753f-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6753f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6753f-110">Remarks</span></span>  
 <span data-ttu-id="6753f-111">Das Element auf der linken Seite des `/=`-Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="6753f-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="6753f-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="6753f-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="6753f-113">Der `/=`-Operator dividiert zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) durch den Wert des Ausdrucks (auf der rechten Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="6753f-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="6753f-114">Der-Operator weist dann das Gleit Komma Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="6753f-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="6753f-115">Diese Anweisung weist der Variablen oder der Eigenschaft auf der linken Seite einen `Double`-Wert zu.</span><span class="sxs-lookup"><span data-stu-id="6753f-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="6753f-116">Wenn `Option Strict` `On` ist, muss `variableorproperty` ein `Double` sein.</span><span class="sxs-lookup"><span data-stu-id="6753f-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="6753f-117">Wenn `Option Strict` `Off` ist, führt Visual Basic eine implizite Konvertierung durch und weist den resultierenden Wert `variableorproperty` mit einem möglichen Fehler zur Laufzeit zu.</span><span class="sxs-lookup"><span data-stu-id="6753f-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="6753f-118">Weitere Informationen finden Sie unter [erweiternde und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6753f-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6753f-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="6753f-119">Overloading</span></span>  
 <span data-ttu-id="6753f-120">Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="6753f-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6753f-121">Das Überladen des `/`-Operators wirkt sich auf das Verhalten des `/=`-Operators aus.</span><span class="sxs-lookup"><span data-stu-id="6753f-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="6753f-122">Wenn Ihr Code `/=` für eine Klasse oder Struktur verwendet, die `/` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="6753f-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6753f-123">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6753f-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6753f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6753f-124">Example</span></span>  
 <span data-ttu-id="6753f-125">Im folgenden Beispiel wird der `/=`-Operator verwendet, um eine `Integer`-Variable durch eine Sekunde zu teilen und den Quotienten der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6753f-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="6753f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6753f-126">See also</span></span>

- [<span data-ttu-id="6753f-127">Operator/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6753f-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="6753f-128">\\ =-Operator</span><span class="sxs-lookup"><span data-stu-id="6753f-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="6753f-129">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="6753f-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="6753f-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="6753f-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="6753f-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6753f-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6753f-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="6753f-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6753f-133">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="6753f-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
