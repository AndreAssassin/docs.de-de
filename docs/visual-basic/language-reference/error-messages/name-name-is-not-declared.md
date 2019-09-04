---
title: Der Name '<name>' wurde nicht deklariert.
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: dfa1d1600c7943e503b4f5ec2e2b8ecd6fbb9fe0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254198"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="6532f-102">Name '\<Name >' ist nicht deklariert</span><span class="sxs-lookup"><span data-stu-id="6532f-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="6532f-103">Eine Anweisung verweist auf ein Programmierelement, aber der Compiler kein Element mit genau diesem Namen gefunden.</span><span class="sxs-lookup"><span data-stu-id="6532f-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="6532f-104">**Fehler-ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="6532f-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6532f-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6532f-105">To correct this error</span></span>  
  
1. <span data-ttu-id="6532f-106">Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6532f-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="6532f-107">Visual Basic ist die Groß-/Kleinschreibung, jedoch eine andere Variante der Schreibweise als einen ganz anderen Namen betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="6532f-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="6532f-108">Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.</span><span class="sxs-lookup"><span data-stu-id="6532f-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="6532f-109">Überprüfen Sie, ob Sie den Memberzugriffsoperator (`.`) zwischen einem Objekt und seine Member.</span><span class="sxs-lookup"><span data-stu-id="6532f-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="6532f-110">Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben.</span><span class="sxs-lookup"><span data-stu-id="6532f-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="6532f-111">Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="6532f-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="6532f-112">Wenn die Schreibweise korrekt ist und die Syntax des Objekts Memberzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="6532f-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="6532f-113">Weitere Informationen finden Sie unter [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="6532f-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="6532f-114">Wenn das Programmierelement deklariert wurde, überprüfen Sie, dass sie im Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="6532f-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="6532f-115">Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie möglicherweise den Namen des zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="6532f-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="6532f-116">Weitere Informationen finden Sie unter [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="6532f-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="6532f-117">Wenn Sie keine voll qualifizierte Typ oder Namen von Typen und Member verwenden (z. B. Ihr Code verweist auf eine Eigenschaft als `MethodInfo.Name` anstelle von `System.Reflection.MethodInfo.Name`), Hinzufügen einer [Imports-Anweisung](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="6532f-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="6532f-118">Wenn Sie versuchen, eine SDK-Projekt zu kompilieren (ein Projekt mit einem \*VBPROJ-Datei, die mit der Zeile beginnt `<Project Sdk="Microsoft.NET.Sdk">`), und die Fehlermeldung verweist auf einen Typ oder Member in der 'Microsoft.VisualBasic.dll'-Assembly, Ihre Anwendung so konfigurieren Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="6532f-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="6532f-119">Standardmäßig wird eine Teilmenge der Bibliothek in die Assembly in einem Projekt von SDK-Stil eingebettet.</span><span class="sxs-lookup"><span data-stu-id="6532f-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="6532f-120">Im folgenden Beispiel wird beispielsweise nicht, kompiliert, da die <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> Methode wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="6532f-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="6532f-121">Es ist nicht in der Teilmenge der Visual Basic-Laufzeit enthalten, die mit Ihrer Anwendung eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="6532f-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   <span data-ttu-id="6532f-122">Um diesen Fehler zu beheben, fügen die `<VBRuntime>Default</VBRuntime>` Element an den Projekten `<PropertyGroup>` Abschnitt, wie im folgenden Visual Basic-Projekt-Datei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6532f-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="6532f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6532f-123">See also</span></span>

- [<span data-ttu-id="6532f-124">Deklarationen und Konstanten: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="6532f-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="6532f-125">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="6532f-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="6532f-126">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="6532f-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="6532f-127">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="6532f-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
