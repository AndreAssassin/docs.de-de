---
title: Partial (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: da5679c3e69a938e9735922bcf4f912428024610
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642779"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="c4831-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4831-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="c4831-103">Gibt an, dass eine Typdeklaration eine partielle Definition des Typs ist.</span><span class="sxs-lookup"><span data-stu-id="c4831-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="c4831-104">Mit dem `Partial`-Schlüsselwort können Sie die Typdefinition auf mehrere Deklarationen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="c4831-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="c4831-105">Sie können beliebig viele partielle Deklarationen in beliebig vielen verschiedenen Quelldateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4831-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="c4831-106">Alle Deklarationen müssen jedoch in der gleichen Assembly und dem gleichen Namespace enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c4831-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4831-107">Visual Basic unterstützt *partielle Methoden*, die in der Regel in partiellen Klassen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c4831-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="c4831-108">Weitere Informationen finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) und [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4831-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4831-109">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="c4831-110">Teile</span><span class="sxs-lookup"><span data-stu-id="c4831-110">Parts</span></span>  
  
|<span data-ttu-id="c4831-111">Begriff</span><span class="sxs-lookup"><span data-stu-id="c4831-111">Term</span></span>|<span data-ttu-id="c4831-112">Definition</span><span class="sxs-lookup"><span data-stu-id="c4831-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="c4831-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-113">Optional.</span></span> <span data-ttu-id="c4831-114">Liste der Attribute, die für diesen Typ gelten.</span><span class="sxs-lookup"><span data-stu-id="c4831-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="c4831-115">Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern (`< >`).</span><span class="sxs-lookup"><span data-stu-id="c4831-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="c4831-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-116">Optional.</span></span> <span data-ttu-id="c4831-117">Gibt an, welcher Code auf diesen Typ zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c4831-117">Specifies what code can access this type.</span></span> <span data-ttu-id="c4831-118">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="c4831-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-119">Optional.</span></span> <span data-ttu-id="c4831-120">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="c4831-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-121">Optional.</span></span> <span data-ttu-id="c4831-122">Finden Sie unter [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="c4831-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-123">Optional.</span></span> <span data-ttu-id="c4831-124">Finden Sie unter [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="c4831-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4831-125">Required.</span></span> <span data-ttu-id="c4831-126">Der Name dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="c4831-126">Name of this type.</span></span> <span data-ttu-id="c4831-127">Muss mit dem Namen übereinstimmen, der in allen anderen partiellen Deklarationen desselben Typs definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c4831-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="c4831-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-128">Optional.</span></span> <span data-ttu-id="c4831-129">Gibt an, dass dies ein generischer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="c4831-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="c4831-130">Finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="c4831-131">Erforderlich, wenn Sie [von](../../../visual-basic/language-reference/statements/of-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="c4831-132">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="c4831-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-133">Optional.</span></span> <span data-ttu-id="c4831-134">Finden Sie unter [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="c4831-135">Erforderlich, wenn Sie `Inherits` verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4831-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="c4831-136">Der Name der Klasse oder Schnittstelle, von der diese Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c4831-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="c4831-137">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-137">Optional.</span></span> <span data-ttu-id="c4831-138">Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="c4831-139">Erforderlich, wenn Sie `Implements` verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4831-139">Required if you use `Implements`.</span></span> <span data-ttu-id="c4831-140">Die Namen der von diesem Typ implementierten Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="c4831-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="c4831-141">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-141">Optional.</span></span> <span data-ttu-id="c4831-142">Anweisungen, die zusätzliche Variablen und Ereignisse für den Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="c4831-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="c4831-143">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4831-143">Optional.</span></span> <span data-ttu-id="c4831-144">Anweisungen, die zusätzliche Prozeduren für den Typ deklarieren und definieren.</span><span class="sxs-lookup"><span data-stu-id="c4831-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="c4831-145">`End Class` oder `End Structure`</span><span class="sxs-lookup"><span data-stu-id="c4831-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="c4831-146">Beendet diese partielle `Class`- oder `Structure`-Definition.</span><span class="sxs-lookup"><span data-stu-id="c4831-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4831-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4831-147">Remarks</span></span>  
 <span data-ttu-id="c4831-148">Visual Basic verwendet partielle Klassendefinitionen, um in jeweils eigenen Quelldateien generierten Code von Code zu trennen, der vom Benutzer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4831-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="c4831-149">Zum Beispiel definiert der **Windows Form-Designer** partielle Klassen für Steuerelemente, z.B. <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="c4831-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="c4831-150">Sie sollten den generierten Code in diesen Steuerelementen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c4831-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="c4831-151">Beim Erstellen eines partiellen Typs gelten alle Regeln für die Erstellung von Klassen, Strukturen, Schnittstellen und Modulen, beispielsweise diejenigen für die Verwendung und Vererbung von Modifizierern.</span><span class="sxs-lookup"><span data-stu-id="c4831-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="c4831-152">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="c4831-152">Best Practices</span></span>  
  
- <span data-ttu-id="c4831-153">Normalerweise wird die Entwicklung eines einzelnen Typs nicht auf zwei oder mehr Deklarationen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="c4831-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="c4831-154">In der Regel benötigen Sie das `Partial`-Schlüsselwort daher nicht.</span><span class="sxs-lookup"><span data-stu-id="c4831-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="c4831-155">Zur besseren Lesbarkeit sollte jede partielle Deklaration eines Typs das `Partial`-Schlüsselwort enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4831-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="c4831-156">Der Compiler gestattet den Wegfall des Schlüsselworts nur bei höchstens einer partiellen Deklaration. Fällt es bei mehr als einer Deklaration weg, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c4831-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c4831-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c4831-157">Behavior</span></span>  
  
- <span data-ttu-id="c4831-158">**Die Union von Deklarationen.**</span><span class="sxs-lookup"><span data-stu-id="c4831-158">**Union of Declarations.**</span></span> <span data-ttu-id="c4831-159">Der Compiler behandelt den Typ als die Union all seiner partiellen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="c4831-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="c4831-160">Jeder Modifizierer aus jeder partiellen Definition wird auf den gesamten Typ angewendet, und jeder Member aus jeder partiellen Definition steht dem gesamten Typ zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c4831-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="c4831-161">**Typerweiterung nicht zulässig für partielle Typen in Modulen.**</span><span class="sxs-lookup"><span data-stu-id="c4831-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="c4831-162">Wenn eine partielle Definition in einem Modul enthalten ist, ist automatisch keine Typerweiterung für diesen Typ möglich.</span><span class="sxs-lookup"><span data-stu-id="c4831-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="c4831-163">In einem solchen Fall kann eine Reihe partieller Definitionen zu unerwarteten Ergebnissen und sogar zu Compilerfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="c4831-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="c4831-164">Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="c4831-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="c4831-165">Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c4831-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="c4831-166">Das `Partial`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c4831-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c4831-167">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4831-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="c4831-168">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4831-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="c4831-169">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4831-169">Example</span></span>  
 <span data-ttu-id="c4831-170">Im folgenden Beispiel wird die Definition der `sampleClass`-Klasse auf zwei Deklarationen aufgeteilt, die jeweils eine andere `Sub`-Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="c4831-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="c4831-171">Die beiden partiellen Definitionen aus dem vorhergehenden Beispiel können in derselben Quelldatei oder in zwei unterschiedlichen Quelldateien enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c4831-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4831-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4831-172">See also</span></span>

- [<span data-ttu-id="c4831-173">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4831-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="c4831-174">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c4831-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="c4831-175">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="c4831-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="c4831-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="c4831-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="c4831-177">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4831-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="c4831-178">Partielle Methoden</span><span class="sxs-lookup"><span data-stu-id="c4831-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
