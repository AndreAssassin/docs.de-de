---
title: '&amp; -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817278"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="86d8b-102">&amp; -Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86d8b-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="86d8b-103">Generiert eine zeichenfolgenverkettung aus zwei Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="86d8b-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86d8b-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="86d8b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="86d8b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="86d8b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86d8b-106">Required.</span></span> <span data-ttu-id="86d8b-107">Alle `String` oder `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="86d8b-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="86d8b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86d8b-108">Required.</span></span> <span data-ttu-id="86d8b-109">Jeder Ausdruck mit einem Datentyp, der auf erweitert wird `String`.</span><span class="sxs-lookup"><span data-stu-id="86d8b-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="86d8b-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="86d8b-110">Required.</span></span> <span data-ttu-id="86d8b-111">Jeder Ausdruck mit einem Datentyp, der auf erweitert wird `String`.</span><span class="sxs-lookup"><span data-stu-id="86d8b-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86d8b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86d8b-112">Remarks</span></span>  
 <span data-ttu-id="86d8b-113">Wenn der Datentyp des `expression1` oder `expression2` nicht `String` jedoch erweitert, um `String`, wird eine Konvertierung in `String`.</span><span class="sxs-lookup"><span data-stu-id="86d8b-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="86d8b-114">Wenn entweder der Datentypen ist nicht zu erweitert `String`, generiert der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="86d8b-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="86d8b-115">Der Datentyp des `result` ist `String`.</span><span class="sxs-lookup"><span data-stu-id="86d8b-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="86d8b-116">Wenn eine oder beide Ausdrücke [nichts](../../../visual-basic/language-reference/nothing.md) oder den Wert der <xref:System.DBNull.Value?displayProperty=nameWithType>, werden sie behandelt, als eine Zeichenfolge mit dem Wert "".</span><span class="sxs-lookup"><span data-stu-id="86d8b-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86d8b-117">Die `&` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="86d8b-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="86d8b-118">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="86d8b-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="86d8b-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="86d8b-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86d8b-120">Das kaufmännische und-Zeichen (&) können auch zum Identifizieren von Variablen als Typ verwendet werden `Long`.</span><span class="sxs-lookup"><span data-stu-id="86d8b-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="86d8b-121">Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="86d8b-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d8b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86d8b-122">Example</span></span>  
 <span data-ttu-id="86d8b-123">Dieses Beispiel verwendet die `&` Operator zum Verketten von Zeichenfolgen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="86d8b-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="86d8b-124">Das Ergebnis ist ein Zeichenfolgenwert, der die Verkettung von den beiden Zeichenfolgenoperanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="86d8b-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="86d8b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86d8b-125">See also</span></span>

- [<span data-ttu-id="86d8b-126">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="86d8b-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="86d8b-127">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="86d8b-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="86d8b-128">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86d8b-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="86d8b-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="86d8b-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="86d8b-130">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86d8b-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
