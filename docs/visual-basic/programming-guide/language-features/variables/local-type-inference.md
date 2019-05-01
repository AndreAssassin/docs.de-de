---
title: Lokaler Typrückschluss (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: e6214938262b987a1bae4a9ca1d5c945f8b7fe6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052585"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="efb44-102">Lokaler Typrückschluss (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efb44-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="efb44-103">Visual Basic-Compiler verwendet *Typrückschluss* um zu bestimmen, die die Datentypen für lokale Variablen deklariert, ohne eine `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="efb44-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="efb44-104">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="efb44-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="efb44-105">Dadurch können Sie Variablen zu deklarieren, ohne explizit einen Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="efb44-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="efb44-106">Als Ergebnis die Deklarationen sowohl `num1` und `num2` sind stark typisiert, als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="efb44-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  <span data-ttu-id="efb44-107">Wenn Sie nicht möchten `num2` im vorherigen Beispiel als typisiert wird ein `Integer`, Sie können einen anderen Typ angeben, indem Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="efb44-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="efb44-108">Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Es kann nicht verwendet werden, um den Typ der Klassenfelder, Eigenschaften oder Funktionen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="efb44-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="efb44-109">Lokaler Typrückschluss gilt auf Prozedurebene.</span><span class="sxs-lookup"><span data-stu-id="efb44-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="efb44-110">Es kann nicht zum Deklarieren von Variablen auf Modulebene (innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder einem Block) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efb44-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="efb44-111">Wenn `num2` im vorherigen Beispiel wurden ein Feld einer Klasse anstelle der lokalen Variablen in einer Prozedur, die Deklaration würde einen Fehler mit `Option Strict` , und klassifizieren `num2` als ein `Object` mit `Option Strict` deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="efb44-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="efb44-112">Auf ähnliche Weise lokaler Typrückschluss gilt nicht für Ebene Prozedur-Variablen, die als `Static`.</span><span class="sxs-lookup"><span data-stu-id="efb44-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="efb44-113">Typrückschluss und Späte Bindung</span><span class="sxs-lookup"><span data-stu-id="efb44-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="efb44-114">Code, der Typrückschluss verwendet ähnelt, Code, der auf die späte Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efb44-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="efb44-115">Typrückschluss Typen jedoch stark der Variablen statt als bleiben `Object`.</span><span class="sxs-lookup"><span data-stu-id="efb44-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="efb44-116">Der Compiler verwendet eine Variable des Initialisierers um den Wert der Variablen zum Zeitpunkt der Kompilierung zum Erzeugen von Code mit früher Bindung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="efb44-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="efb44-117">Im vorherigen Beispiel `num2`, z. B. `num1`, typisiert ist, als ein `Integer`.</span><span class="sxs-lookup"><span data-stu-id="efb44-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="efb44-118">Das Verhalten der früh gebundene Variablen unterscheidet sich von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="efb44-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="efb44-119">Die den Typ einem frühen Zeitpunkt kann der Compiler Probleme vor der Ausführung zu identifizieren, Speicher genau zuordnen und Durchführen weiterer Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="efb44-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="efb44-120">Früher Bindung ermöglicht auch die integrierte Entwicklungsumgebung (IDE) zum Bereitstellen von IntelliSense-Hilfe zu den Elementen eines Objekts von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="efb44-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="efb44-121">Früher Bindung wird auch bevorzugt, für die Leistung.</span><span class="sxs-lookup"><span data-stu-id="efb44-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="efb44-122">Dies ist, da alle Daten in eine spät gebundene Variable müssen, als Typ eingebunden sein `Object`, und das Zugreifen auf Member des Typs zur Laufzeit wird das Programm, die langsamer.</span><span class="sxs-lookup"><span data-stu-id="efb44-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="efb44-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="efb44-123">Examples</span></span>  
 <span data-ttu-id="efb44-124">Typrückschluss tritt auf, wenn eine lokale Variable, ohne deklariert wird eine `As` Klausel und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="efb44-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="efb44-125">Der Compiler verwendet den Typ des ersten zugewiesenen Werts als Typ der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="efb44-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="efb44-126">Die folgenden Zeilen des Codes deklariert beispielsweise eine Variable vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="efb44-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 <span data-ttu-id="efb44-127">Der folgende Code veranschaulicht zwei gleichwertige Möglichkeiten zum Erstellen eines Arrays von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="efb44-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 <span data-ttu-id="efb44-128">Es ist sinnvoll, den Typrückschluss verwenden, um den Typ des eine Schleifensteuerungsvariable zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="efb44-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="efb44-129">In den folgenden Code, der Compiler leitet ab, die `number` ist ein `Integer` da `someNumbers2` aus dem vorherigen Beispiel wird ein Array von ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="efb44-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 <span data-ttu-id="efb44-130">Lokaler Typrückschluss verwendet werden kann, `Using` Anweisungen zu, um den Typ des Ressourcennamens, herzustellen, wie das folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="efb44-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 <span data-ttu-id="efb44-131">Der Typ einer Variablen kann auch von die Rückgabewerte von Funktionen, die abgeleitet werden, wie das folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="efb44-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="efb44-132">Beide `pList1` und `pList2` werden Arrays von Prozessen, da `Process.GetProcesses` gibt ein Array von Prozessen.</span><span class="sxs-lookup"><span data-stu-id="efb44-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a><span data-ttu-id="efb44-133">Option Infer-</span><span class="sxs-lookup"><span data-stu-id="efb44-133">Option Infer</span></span>  
 <span data-ttu-id="efb44-134">`Option Infer` ermöglicht, die Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="efb44-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="efb44-135">Aktivieren oder blockieren die Option, geben Sie einen der folgenden Anweisungen am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="efb44-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="efb44-136">Wenn Sie einen Wert für nicht angeben `Option Infer` in Ihrem Code ist die Standardeinstellung des Compilers `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="efb44-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="efb44-137">Für Projekte von aktualisierten [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] oder früher, die Standardeinstellung des Compilers ist `Option Infer Off`.</span><span class="sxs-lookup"><span data-stu-id="efb44-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="efb44-138">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="efb44-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="efb44-139">Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="efb44-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb44-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efb44-140">See also</span></span>

- [<span data-ttu-id="efb44-141">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="efb44-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="efb44-142">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="efb44-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="efb44-143">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efb44-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="efb44-144">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efb44-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="efb44-145">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="efb44-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="efb44-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="efb44-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="efb44-147">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efb44-147">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
