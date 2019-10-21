---
title: Operatorprozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 46afbbe411a1adf27960e3c7d9d3ca98046ecec5
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524524"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="e915a-102">Operatorprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e915a-102">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="e915a-103">Eine Operator Prozedur ist eine Reihe von Visual Basic-Anweisungen, die das Verhalten eines Standard Operators (z. b. `*`, `<>` oder `And`) für eine von Ihnen definierte Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="e915a-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="e915a-104">Dies wird auch als *Operator Überladung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e915a-104">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="e915a-105">Definieren von Operator Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-105">When to Define Operator Procedures</span></span>

<span data-ttu-id="e915a-106">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Variablen so deklarieren, dass Sie vom Typ dieser Klasse oder Struktur sind.</span><span class="sxs-lookup"><span data-stu-id="e915a-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="e915a-107">Manchmal muss eine solche Variable an einem Vorgang als Teil eines Ausdrucks teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="e915a-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="e915a-108">Zu diesem Zweck muss Sie ein Operand eines Operators sein.</span><span class="sxs-lookup"><span data-stu-id="e915a-108">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="e915a-109">Visual Basic definiert Operatoren nur für die grundlegenden Datentypen.</span><span class="sxs-lookup"><span data-stu-id="e915a-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="e915a-110">Sie können das Verhalten eines Operators definieren, wenn einer oder beide Operanden vom Typ der Klasse oder Struktur sind.</span><span class="sxs-lookup"><span data-stu-id="e915a-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="e915a-111">Weitere Informationen finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e915a-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="e915a-112">Typen von Operator Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-112">Types of Operator Procedure</span></span>

<span data-ttu-id="e915a-113">Eine Operator Prozedur kann einen der folgenden Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e915a-113">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="e915a-114">Eine Definition eines unären Operators, bei dem das Argument vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="e915a-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="e915a-115">Eine Definition eines binären Operators, bei der mindestens eines der Argumente vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="e915a-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="e915a-116">Eine Definition eines Konvertierungs Operators, bei der das Argument vom Typ der Klasse oder Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="e915a-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="e915a-117">Eine Definition eines Konvertierungs Operators, der den Typ der Klasse oder Struktur zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e915a-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="e915a-118">Konvertierungs Operatoren sind immer Unär, und Sie verwenden immer `CType` als den Operator, den Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="e915a-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="e915a-119">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="e915a-119">Declaration Syntax</span></span>

<span data-ttu-id="e915a-120">Die Syntax zum Deklarieren einer Operator Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e915a-120">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="e915a-121">Sie verwenden das Schlüsselwort `Widening` oder `Narrowing` nur für einen Typkonvertierungs Operator.</span><span class="sxs-lookup"><span data-stu-id="e915a-121">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="e915a-122">Das Operator Symbol ist immer [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) für einen Typkonvertierungs Operator.</span><span class="sxs-lookup"><span data-stu-id="e915a-122">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="e915a-123">Sie deklarieren zwei Operanden, um einen binären Operator zu definieren, und Sie deklarieren einen Operanden, um einen unären Operator, einschließlich eines Typkonvertierungs Operators, zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e915a-123">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="e915a-124">Alle Operanden müssen als `ByVal` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="e915a-124">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="e915a-125">Sie deklarieren jeden Operanden auf dieselbe Weise, wie Sie Parameter für [unter Prozeduren](./sub-procedures.md)deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e915a-125">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="e915a-126">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e915a-126">Data Type</span></span>

<span data-ttu-id="e915a-127">Da Sie einen Operator in einer Klasse oder Struktur definieren, die Sie definiert haben, muss mindestens einer der Operanden vom Datentyp dieser Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="e915a-127">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="e915a-128">Für einen Typkonvertierungs Operator muss entweder der Operand oder der Rückgabetyp vom Datentyp der Klasse oder Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="e915a-128">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="e915a-129">Weitere Informationen finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e915a-129">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="e915a-130">Aufruf Syntax</span><span class="sxs-lookup"><span data-stu-id="e915a-130">Calling Syntax</span></span>

<span data-ttu-id="e915a-131">Sie rufen eine Operator Prozedur implizit mithilfe des-Operator Symbols in einem Ausdruck auf.</span><span class="sxs-lookup"><span data-stu-id="e915a-131">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="e915a-132">Sie stellen die Operanden auf die gleiche Weise wie für vordefinierte Operatoren bereit.</span><span class="sxs-lookup"><span data-stu-id="e915a-132">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="e915a-133">Die Syntax für einen impliziten aufrufsvorgang für eine Operator Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e915a-133">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="e915a-134">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="e915a-134">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="e915a-135">`Dim testNewStruct As`*structurename* `= testStruct`*Operatorsymbol* `10`</span><span class="sxs-lookup"><span data-stu-id="e915a-135">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="e915a-136">Abbildung der Deklaration und des Aufruf</span><span class="sxs-lookup"><span data-stu-id="e915a-136">Illustration of Declaration and Call</span></span>

<span data-ttu-id="e915a-137">In der folgenden Struktur wird ein ganzzahliger 128-Bit-ganzzahliger Wert als die einzelnen Teile der Reihenfolge und der unteren Reihenfolge gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e915a-137">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="e915a-138">Er definiert den `+`-Operator, um zwei `veryLong` Werte hinzuzufügen und einen resultierenden `veryLong` Wert zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e915a-138">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="e915a-139">Das folgende Beispiel zeigt einen typischen aufrufsoperator, `+` der für `veryLong` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e915a-139">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="e915a-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e915a-140">See also</span></span>

- [<span data-ttu-id="e915a-141">Verfahren</span><span class="sxs-lookup"><span data-stu-id="e915a-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e915a-142">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-142">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e915a-143">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="e915a-144">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e915a-145">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e915a-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e915a-146">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e915a-146">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="e915a-147">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="e915a-147">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="e915a-148">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="e915a-148">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="e915a-149">Gewusst wie: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="e915a-149">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="e915a-150">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert</span><span class="sxs-lookup"><span data-stu-id="e915a-150">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
