---
title: 'Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: c14aa35ce15549ad9eccabe2330a7c43b6795140
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864701"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="28cba-102">Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28cba-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="28cba-103">Sollten Sie ermitteln, ob einen Ausdruck, der die [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) einem Muster entspricht, dann können Sie mithilfe der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28cba-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="28cba-104">`Like` akzeptiert zwei Operanden.</span><span class="sxs-lookup"><span data-stu-id="28cba-104">`Like` takes two operands.</span></span> <span data-ttu-id="28cba-105">Der linke Operand ist ein Zeichenfolgenausdruck, und der Rechte Operand ist eine Zeichenfolge, enthält das Muster für den Abgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28cba-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="28cba-106">`Like` Gibt eine `Boolean` Wert, der angibt, ob der Ausdruck mit dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="28cba-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="28cba-107">Sie können jedes Zeichen in den Ausdruck für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einen Zeichenbereich zuordnen.</span><span class="sxs-lookup"><span data-stu-id="28cba-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="28cba-108">Die Positionen der Angaben in der Musterzeichenfolge entsprechen die Positionen der Zeichen im Zeichenfolgenausdruck abgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="28cba-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="28cba-109">Um ein Zeichen in den Ausdruck für ein bestimmtes Zeichen</span><span class="sxs-lookup"><span data-stu-id="28cba-109">To match a character in the string expression against a specific character</span></span>  
  
- <span data-ttu-id="28cba-110">Fügen Sie das Zeichen direkt in der Musterzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="28cba-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="28cba-111">Bestimmte Sonderzeichen müssen in Klammern eingeschlossen werden (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="28cba-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="28cba-112">Weitere Informationen finden Sie unter [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28cba-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="28cba-113">Im folgenden Beispiel wird getestet, ob `myString` besteht genau aus das einzelne Zeichen `H`.</span><span class="sxs-lookup"><span data-stu-id="28cba-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="28cba-114">Um ein Zeichen in den Ausdruck mit einem Platzhalterzeichen</span><span class="sxs-lookup"><span data-stu-id="28cba-114">To match a character in the string expression against a wildcard character</span></span>  
  
- <span data-ttu-id="28cba-115">Fügen ein Fragezeichen (`?`) in der Musterzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="28cba-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="28cba-116">Jedes gültige Zeichen an dieser Position ergibt eine Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="28cba-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="28cba-117">Im folgenden Beispiel wird getestet, ob `myString` besteht aus den einzelnen Zeichens `W` gefolgt von genau zwei beliebigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="28cba-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="28cba-118">Um ein Zeichen in den Zeichenfolgenausdruck mit einer Liste von Zeichen</span><span class="sxs-lookup"><span data-stu-id="28cba-118">To match a character in the string expression against a list of characters</span></span>  
  
- <span data-ttu-id="28cba-119">Einfügen von Klammern (`[ ]`) in der Musterzeichenfolge, und klicken Sie in den Klammern fügen Sie die Liste von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="28cba-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="28cba-120">Trennen Sie die Zeichen nicht mit Kommas oder aller anderen Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="28cba-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="28cba-121">Beliebiges einzelnes Zeichen in der Liste wird eine Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="28cba-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="28cba-122">Im folgenden Beispiel wird getestet, ob `myString` irgendeinem gültigen Zeichen, gefolgt von genau einem Zeichen bestehen `A`, `C`, oder `E`.</span><span class="sxs-lookup"><span data-stu-id="28cba-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="28cba-123">Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="28cba-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="28cba-124">Um ein Zeichen in den Ausdruck für einen Bereich von Zeichen</span><span class="sxs-lookup"><span data-stu-id="28cba-124">To match a character in the string expression against a range of characters</span></span>  
  
- <span data-ttu-id="28cba-125">Einfügen von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern, die die niedrigsten und höchsten Zeichen im Bereich einfügen, getrennt durch einen Bindestrich (`–`).</span><span class="sxs-lookup"><span data-stu-id="28cba-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="28cba-126">Beliebiges einzelnes Zeichen innerhalb des Bereichs ergibt eine Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="28cba-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="28cba-127">Im folgenden Beispiel wird getestet, ob `myString` besteht aus den Zeichen `num` gefolgt von genau einem Zeichen `i`, `j`, `k`, `l`, `m`, oder `n`.</span><span class="sxs-lookup"><span data-stu-id="28cba-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="28cba-128">Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="28cba-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="28cba-129">Übereinstimmende leere Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="28cba-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="28cba-130">`Like` behandelt die Sequenz `[]` als eine Zeichenfolge der Länge 0 (null) (`""`).</span><span class="sxs-lookup"><span data-stu-id="28cba-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="28cba-131">Sie können `[]` zu prüfen, ob der gesamte Ausdruck leer ist, aber Sie können keine sie prüfen, ob eine bestimmte Position im Zeichenfolgenausdruck leer ist.</span><span class="sxs-lookup"><span data-stu-id="28cba-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="28cba-132">Eine der Optionen ist eine leere Position müssen Sie testen, für die Sie verwenden können, `Like` mehr als einmal.</span><span class="sxs-lookup"><span data-stu-id="28cba-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="28cba-133">Um ein Zeichen in den Ausdruck anhand einer Liste von Zeichen oder keine Zeichen</span><span class="sxs-lookup"><span data-stu-id="28cba-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1. <span data-ttu-id="28cba-134">Rufen Sie die `Like` Operator zwei Mal auf dem gleichen Ausdruck eine Zeichenfolge, und verbinden Sie die beiden Aufrufe entweder mit der [oder-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) oder [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28cba-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2. <span data-ttu-id="28cba-135">In der Musterzeichenfolge für die erste `Like` -Klausel, die in Klammern eingeschlossene Zeichenliste enthalten (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="28cba-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3. <span data-ttu-id="28cba-136">In der Musterzeichenfolge für die zweite `Like` -Klausel, platzieren Sie keines Zeichen an der Position betreffende.</span><span class="sxs-lookup"><span data-stu-id="28cba-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="28cba-137">Das folgende Beispiel testet die siebenstelligen Telefonnummer `phoneNum` für genau drei Ziffern, gefolgt von einem Leerzeichen, einen Bindestrich (`–`), einen Zeitraum (`.`), oder keine, gefolgt von genau vier Ziffern.</span><span class="sxs-lookup"><span data-stu-id="28cba-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="28cba-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28cba-138">See also</span></span>

- [<span data-ttu-id="28cba-139">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="28cba-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="28cba-140">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="28cba-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="28cba-141">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="28cba-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="28cba-142">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="28cba-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
