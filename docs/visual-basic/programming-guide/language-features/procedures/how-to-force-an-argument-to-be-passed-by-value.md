---
title: 'Vorgehensweise: Erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 540271c414ac295c419533a4622657d60d123796
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665392"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="5d733-102">Vorgehensweise: Erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden</span><span class="sxs-lookup"><span data-stu-id="5d733-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="5d733-103">Den Übergabemechanismus der Prozedurdeklaration.</span><span class="sxs-lookup"><span data-stu-id="5d733-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="5d733-104">Wenn ein Parameter deklariert wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic geht davon aus, das entsprechende Argument als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="5d733-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="5d733-105">Dadurch wird das Verfahren zum Ändern des Werts des zugrunde liegenden Arguments im aufrufenden Code Programmierelements.</span><span class="sxs-lookup"><span data-stu-id="5d733-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="5d733-106">Wenn Sie das zugrunde liegende Element für eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` Übergabemechanismus in der Prozedur aufrufen, indem der Name des Arguments in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="5d733-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="5d733-107">Diese Klammern sind zusätzlich zu den Klammern einschließen der Liste der Argumente im Aufruf.</span><span class="sxs-lookup"><span data-stu-id="5d733-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="5d733-108">Der aufrufende Code kann nicht überschrieben. eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="5d733-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="5d733-109">Erzwingen Sie ein Argument als Wert übergeben werden</span><span class="sxs-lookup"><span data-stu-id="5d733-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="5d733-110">Wenn der entsprechende Parameter deklariert wird `ByVal` in der Prozedur, Sie müssen keine weiteren Schritte.</span><span class="sxs-lookup"><span data-stu-id="5d733-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="5d733-111">Visual Basic erwartet, dass bereits das Argument als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="5d733-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="5d733-112">Wenn der entsprechende Parameter deklariert wird `ByRef` setzen Sie in der Prozedur das Argument im Aufruf Prozedur in Klammern.</span><span class="sxs-lookup"><span data-stu-id="5d733-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d733-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d733-113">Example</span></span>  
 <span data-ttu-id="5d733-114">Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration.</span><span class="sxs-lookup"><span data-stu-id="5d733-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="5d733-115">Im Aufruf, die erzwingt, dass `ByVal`, beachten Sie die zwei Ebenen von Klammern.</span><span class="sxs-lookup"><span data-stu-id="5d733-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="5d733-116">Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist die `setNewString` Prozedur Wert im aufrufenden Code nicht ändern kann und `MsgBox` zeigt "Kann nicht ersetzt werden, wenn ByVal übergeben".</span><span class="sxs-lookup"><span data-stu-id="5d733-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="5d733-117">Wenn `str` ist nicht eingeschlossen in zusätzlichen Klammern kann die Prozedur ändern, und `MsgBox` zeigt "Dies ist es sich um einen neuen Wert für das Argument InString."</span><span class="sxs-lookup"><span data-stu-id="5d733-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d733-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5d733-118">Compiling the Code</span></span>  
 <span data-ttu-id="5d733-119">Wenn Sie eine Variable als Verweis übergeben, müssen Sie verwenden die `ByRef` Schlüsselwort, um diesen Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="5d733-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="5d733-120">Der Standardwert in Visual Basic ist, Argumente als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="5d733-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="5d733-121">Allerdings ist es guter Programmierstil, auch die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für jeden deklarierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="5d733-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="5d733-122">Dadurch wird Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="5d733-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5d733-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="5d733-123">Robust Programming</span></span>  
 <span data-ttu-id="5d733-124">Wenn eine Prozedur einen Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die richtige Ausführung des Codes abhängen, wird das zugrunde liegende Element im aufrufenden Code ändern können.</span><span class="sxs-lookup"><span data-stu-id="5d733-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="5d733-125">Wenn der aufrufende Code diesen Mechanismus aufrufen, überschreibt indem Sie das Argument in Klammern einschließen, oder wenn ein nicht änderbarer Argument übergeben, kann die Prozedur nicht das zugrunde liegende Element ändern.</span><span class="sxs-lookup"><span data-stu-id="5d733-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="5d733-126">Dies kann unerwartete Ergebnisse im aufrufenden Code erzeugen.</span><span class="sxs-lookup"><span data-stu-id="5d733-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5d733-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5d733-127">.NET Framework Security</span></span>  
 <span data-ttu-id="5d733-128">Es ist immer ein potenzielles Risiko einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="5d733-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="5d733-129">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und auf Gültigkeit überprüft werden vor der Verwendung vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="5d733-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d733-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d733-130">See also</span></span>

- [<span data-ttu-id="5d733-131">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5d733-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5d733-132">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5d733-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5d733-133">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="5d733-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="5d733-134">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="5d733-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="5d733-135">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="5d733-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="5d733-136">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="5d733-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="5d733-137">Vorgehensweise: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="5d733-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="5d733-138">Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="5d733-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="5d733-139">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="5d733-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="5d733-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="5d733-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
