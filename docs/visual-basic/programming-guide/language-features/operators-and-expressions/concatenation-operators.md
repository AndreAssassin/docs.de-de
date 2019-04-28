---
title: Verkettungsoperatoren in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: 124f0ca0cd01d7fd218fd89dfb78e70fe8aad9e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864933"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="94269-102">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94269-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="94269-103">Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="94269-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="94269-104">Es gibt zwei Verkettungsoperatoren: `+` und `&`.</span><span class="sxs-lookup"><span data-stu-id="94269-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="94269-105">Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="94269-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="94269-106">Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="94269-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="94269-107">Unterschiede zwischen den beiden Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="94269-107">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="94269-108">Die [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) ist den primären Zweck von zwei Zahlen zu addieren.</span><span class="sxs-lookup"><span data-stu-id="94269-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="94269-109">Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="94269-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="94269-110">Der `+`-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>-Ausnahme bei Laufzeit ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="94269-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="94269-111">Die [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) ist nur für definiert `String` -Operanden verwendet und erweitert seine Operanden, immer `String`, unabhängig von der Einstellung der `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="94269-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="94269-112">Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.</span><span class="sxs-lookup"><span data-stu-id="94269-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="94269-113">Leistung: Zeichenfolge und StringBuilder</span><span class="sxs-lookup"><span data-stu-id="94269-113">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="94269-114">Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>-Klasse im <xref:System.Text>-Namespace profitieren.</span><span class="sxs-lookup"><span data-stu-id="94269-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="94269-115">Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.</span><span class="sxs-lookup"><span data-stu-id="94269-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94269-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94269-116">See also</span></span>

- [<span data-ttu-id="94269-117">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="94269-117">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="94269-118">Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94269-118">Types of String Manipulation Methods in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [<span data-ttu-id="94269-119">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94269-119">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="94269-120">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94269-120">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="94269-121">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94269-121">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
