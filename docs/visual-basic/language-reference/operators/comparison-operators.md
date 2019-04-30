---
title: Vergleichsoperatoren (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013581"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="e967d-102">Vergleichsoperatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e967d-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="e967d-103">Es folgen die Vergleichsoperatoren in Visual Basic definiert.</span><span class="sxs-lookup"><span data-stu-id="e967d-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="e967d-104">`<` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-104">`<` operator</span></span>  
  
 <span data-ttu-id="e967d-105">`<=` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-105">`<=` operator</span></span>  
  
 <span data-ttu-id="e967d-106">`>` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-106">`>` operator</span></span>  
  
 <span data-ttu-id="e967d-107">`>=` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-107">`>=` operator</span></span>  
  
 <span data-ttu-id="e967d-108">`=` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-108">`=` operator</span></span>  
  
 <span data-ttu-id="e967d-109">`<>` Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="e967d-110">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="e967d-111">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="e967d-112">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="e967d-113">Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob sie gleich sind, und falls nicht, wie sie sich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e967d-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="e967d-114">`Is`, `IsNot`, und `Like` werden auf separaten Hilfeseiten ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="e967d-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="e967d-115">Die relationalen Vergleichsoperatoren werden auf dieser Seite im Detail erläutert.</span><span class="sxs-lookup"><span data-stu-id="e967d-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e967d-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="e967d-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="e967d-117">Teile</span><span class="sxs-lookup"><span data-stu-id="e967d-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="e967d-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-118">Required.</span></span> <span data-ttu-id="e967d-119">Ein `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="e967d-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="e967d-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-120">Required.</span></span> <span data-ttu-id="e967d-121">Beliebiger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e967d-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="e967d-122">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-122">Required.</span></span> <span data-ttu-id="e967d-123">Jede relationale Vergleichsoperator.</span><span class="sxs-lookup"><span data-stu-id="e967d-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="e967d-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="e967d-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="e967d-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-125">Required.</span></span> <span data-ttu-id="e967d-126">Jeder Verweis zu verwendenden Objektnamen.</span><span class="sxs-lookup"><span data-stu-id="e967d-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="e967d-127">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-127">Required.</span></span> <span data-ttu-id="e967d-128">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e967d-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="e967d-129">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e967d-129">Required.</span></span> <span data-ttu-id="e967d-130">Alle `String` Ausdruck oder einen Bereich von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e967d-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e967d-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e967d-131">Remarks</span></span>  
 <span data-ttu-id="e967d-132">Die folgende Tabelle enthält eine Liste mit der relationalen Vergleichsoperatoren und die Bedingungen, die bestimmen, ob `result` ist `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="e967d-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="e967d-133">Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-133">Operator</span></span>|<span data-ttu-id="e967d-134">`True`, wenn</span><span class="sxs-lookup"><span data-stu-id="e967d-134">`True` if</span></span>|<span data-ttu-id="e967d-135">`False`, wenn</span><span class="sxs-lookup"><span data-stu-id="e967d-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="e967d-136">`<` (Kleiner als)</span><span class="sxs-lookup"><span data-stu-id="e967d-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="e967d-137">`<=` (Kleiner als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="e967d-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="e967d-138">`>` (Größer als)</span><span class="sxs-lookup"><span data-stu-id="e967d-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="e967d-139">`>=` (Größer als oder gleich)</span><span class="sxs-lookup"><span data-stu-id="e967d-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="e967d-140">`=` (Gleich)</span><span class="sxs-lookup"><span data-stu-id="e967d-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="e967d-141">`<>` (Ungleich)</span><span class="sxs-lookup"><span data-stu-id="e967d-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="e967d-142">Die [= (Operator)](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungsoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="e967d-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="e967d-143">Die `Is` -Operator, der `IsNot` -Operator, und die `Like` Operator haben bestimmten Vergleich von Funktionen, die von den Operatoren in der obigen Tabelle unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e967d-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="e967d-144">Vergleichen von Zahlen</span><span class="sxs-lookup"><span data-stu-id="e967d-144">Comparing Numbers</span></span>  
 <span data-ttu-id="e967d-145">Sie vergleichen, wenn einen Ausdruck vom Typ `Single` eines Typs `Double`, `Single` Ausdruck konvertiert wird `Double`.</span><span class="sxs-lookup"><span data-stu-id="e967d-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="e967d-146">Dieses Verhalten ist Gegensatz zu dem Verhalten in Visual Basic 6.</span><span class="sxs-lookup"><span data-stu-id="e967d-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="e967d-147">Wenn Sie auf ähnliche Weise einen Ausdruck vom Typ vergleichen `Decimal` auf einen Ausdruck vom Typ `Single` oder `Double`, `Decimal` Ausdruck konvertiert wird `Single` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="e967d-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="e967d-148">Für `Decimal` Ausdrücke anteilige Wert kleiner als 1E-28 möglicherweise verloren.</span><span class="sxs-lookup"><span data-stu-id="e967d-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="e967d-149">Solche anteilige Wert möglicherweise zum Verlust zwei Werte als gleich verglichen werden soll, wenn sie nicht sind.</span><span class="sxs-lookup"><span data-stu-id="e967d-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="e967d-150">Aus diesem Grund sollten Sie darauf achten, wenn Gleichheit mit (`=`), zwei Gleitkommavariablen verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e967d-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="e967d-151">Es ist sicherer, testen, ob der Absolute Wert des Unterschieds zwischen den beiden Zahlen, die kleiner als eine kleine akzeptable Toleranz ist.</span><span class="sxs-lookup"><span data-stu-id="e967d-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="e967d-152">Gleitkomma Ungenauigkeit</span><span class="sxs-lookup"><span data-stu-id="e967d-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="e967d-153">Beim Arbeiten mit Gleitkommazahlen, Bedenken Sie, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="e967d-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="e967d-154">Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und [Mod-Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e967d-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="e967d-155">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e967d-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="e967d-156">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e967d-156">Comparing Strings</span></span>  
 <span data-ttu-id="e967d-157">Wenn Sie Zeichenfolgen vergleichen, die Zeichenfolgenausdrücke werden ausgewertet basierend auf ihrer alphabetische Sortierreihenfolge, auf die die `Option Compare` festlegen.</span><span class="sxs-lookup"><span data-stu-id="e967d-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="e967d-158">`Option Compare Binary` Führt einen Zeichenfolgenvergleich auf einer Sortierreihenfolge, die von der internen binären Darstellungen der Zeichen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e967d-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="e967d-159">Die Sortierreihenfolge wird durch die Codepage bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e967d-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="e967d-160">Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="e967d-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="e967d-161">`Option Compare Text` Führt einen Zeichenfolgenvergleich auf einer Groß-/Kleinschreibung, Text Sortierreihenfolge, die vom Gebietsschema der Anwendung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e967d-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="e967d-162">Wenn Sie festlegen, `Option Compare Text` und die Zeichen im vorherigen Beispiel sortieren, gilt die folgende Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="e967d-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="e967d-163">Abhängigkeit vom Gebietsschema</span><span class="sxs-lookup"><span data-stu-id="e967d-163">Locale Dependence</span></span>  
 <span data-ttu-id="e967d-164">Wenn Sie festlegen, `Option Compare Text`, kann das Ergebnis eines Zeichenfolgenvergleichs abhängen, auf dem Gebietsschema, in dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e967d-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="e967d-165">Zwei Zeichen möglicherweise als gleichwertig, die in einem Gebietsschema aber nicht in einer anderen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="e967d-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="e967d-166">Wenn Sie einen Zeichenfolgenvergleich verwenden, z. B. an, ob eine anzunehmen, sich anzumelden, wichtige Entscheidungen treffen sollten Sie die Warnung, die Gebietsschema-Vertraulichkeit sein.</span><span class="sxs-lookup"><span data-stu-id="e967d-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="e967d-167">Sollten Sie entweder die Einstellung `Option Compare Binary` oder die aufrufenden die <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, der das Gebietsschema berücksichtigt akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e967d-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="e967d-168">Programmierung ohne Datentypen mit relationalen Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e967d-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="e967d-169">Die Verwendung von relationalen Vergleichsoperatoren mit `Object` Ausdrücke ist nicht zulässig, unter `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="e967d-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="e967d-170">Wenn `Option Strict` ist `Off`, und entweder `expression1` oder `expression2` ist ein `Object` Ausdruck, der Runtime-Typen zu ermitteln, wie sie verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e967d-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="e967d-171">Die folgende Tabelle zeigt, wie die Ausdrücke verglichen werden und das Ergebnis des Vergleichs, je nach den Laufzeittyp der Operanden.</span><span class="sxs-lookup"><span data-stu-id="e967d-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="e967d-172">Wenn die Operanden sind</span><span class="sxs-lookup"><span data-stu-id="e967d-172">If operands are</span></span>|<span data-ttu-id="e967d-173">Vergleich</span><span class="sxs-lookup"><span data-stu-id="e967d-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="e967d-174">Beide `String`</span><span class="sxs-lookup"><span data-stu-id="e967d-174">Both `String`</span></span>|<span data-ttu-id="e967d-175">Vergleich basierend auf Eigenschaften zum Sortieren von Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="e967d-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="e967d-176">Numerische</span><span class="sxs-lookup"><span data-stu-id="e967d-176">Both numeric</span></span>|<span data-ttu-id="e967d-177">Objekte in konvertiert `Double`, numerischen Vergleich.</span><span class="sxs-lookup"><span data-stu-id="e967d-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="e967d-178">Eine numerische und eine `String`</span><span class="sxs-lookup"><span data-stu-id="e967d-178">One numeric and one `String`</span></span>|<span data-ttu-id="e967d-179">Die `String` konvertiert wird, um eine `Double` und numerischen Vergleich wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e967d-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="e967d-180">Wenn die `String` kann nicht konvertiert werden, um `Double`, <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e967d-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="e967d-181">Eine oder beide sind Verweistypen außer `String`</span><span class="sxs-lookup"><span data-stu-id="e967d-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="e967d-182">Es wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e967d-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="e967d-183">Behandeln von numerische vergleichen `Nothing` als 0.</span><span class="sxs-lookup"><span data-stu-id="e967d-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="e967d-184">Vergleich von Zeichenfolgen behandelt `Nothing` als `""` (eine leere Zeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="e967d-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e967d-185">Überladen</span><span class="sxs-lookup"><span data-stu-id="e967d-185">Overloading</span></span>  
 <span data-ttu-id="e967d-186">Die relationalen Vergleichsoperatoren (`<`.</span><span class="sxs-lookup"><span data-stu-id="e967d-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="e967d-187">`<=``>`, `>=`, `=`, `<>`) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur deren Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="e967d-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e967d-188">Wenn Ihr Code einen dieser Operatoren für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="e967d-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="e967d-189">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e967d-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="e967d-190">Beachten Sie, dass die [= (Operator)](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationale Vergleichsoperator und als Zuweisungsoperator nicht überladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e967d-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e967d-191">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e967d-191">Example</span></span>  
 <span data-ttu-id="e967d-192">Das folgende Beispiel zeigt verschiedene Einsatzbereiche der relationalen Vergleichsoperatoren, die Sie zum Vergleich von Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="e967d-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="e967d-193">Zurückgeben der relationale Vergleichsoperator eine `Boolean` Ergebnis, das angibt, ob der angegebene Ausdruck ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="e967d-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="e967d-194">Beim Anwenden der `>` und `<` Operatoren in Zeichenfolgen, der Vergleich erfolgt mithilfe der normalen Reihenfolge der alphabetischen Sortierung der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e967d-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="e967d-195">Diese Reihenfolge kann abhängig von der gebietsschemaeinstellung sein.</span><span class="sxs-lookup"><span data-stu-id="e967d-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="e967d-196">Abhängig davon, ob die Sortierung Groß-/Kleinschreibung beachtet wird die [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) festlegen.</span><span class="sxs-lookup"><span data-stu-id="e967d-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 <span data-ttu-id="e967d-197">Im vorherigen Beispiel gibt der erste Vergleich `False` und die verbleibenden Vergleiche zurückgeben `True`.</span><span class="sxs-lookup"><span data-stu-id="e967d-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e967d-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e967d-198">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="e967d-199">=-Operator</span><span class="sxs-lookup"><span data-stu-id="e967d-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="e967d-200">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e967d-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e967d-201">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e967d-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e967d-202">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="e967d-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="e967d-203">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e967d-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
