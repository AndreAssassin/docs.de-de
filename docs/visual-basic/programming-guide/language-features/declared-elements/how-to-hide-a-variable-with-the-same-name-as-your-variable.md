---
title: 'Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 744c7aed50690d5591d1e8248e121cb66ef39108
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296185"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="857f3-102">Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="857f3-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="857f3-103">Sie können eine Variable durch ausblenden *shadowing* es, d. h. durch ihn mit einer Variablen mit dem gleichen Namen neu zu definieren.</span><span class="sxs-lookup"><span data-stu-id="857f3-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="857f3-104">Sie können die Variable Schattenkopien, die Sie auf zwei Arten ausblenden möchten:</span><span class="sxs-lookup"><span data-stu-id="857f3-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
-   **<span data-ttu-id="857f3-105">Shadowings über den Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="857f3-105">Shadowing Through Scope.</span></span>** <span data-ttu-id="857f3-106">Sie können ein Shadowing über den Gültigkeitsbereich durch eine erneute Deklaration innerhalb eines Unterbereichs des Bereichs, enthält die Variable, die Sie ausblenden möchten.</span><span class="sxs-lookup"><span data-stu-id="857f3-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
-   **<span data-ttu-id="857f3-107">Shadowings durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="857f3-107">Shadowing Through Inheritance.</span></span>** <span data-ttu-id="857f3-108">Wenn die Variable, die Sie ausblenden möchten, die auf Klassenebene definiert ist, können Sie ein Shadowing über Vererbung durch eine erneute Deklaration mit der [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="857f3-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="857f3-109">Zwei Möglichkeiten zum Ausblenden einer Variablenverweis</span><span class="sxs-lookup"><span data-stu-id="857f3-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="857f3-110">Um einer Variablen ausblenden, indem Sie es über den Gültigkeitsbereich shadowing</span><span class="sxs-lookup"><span data-stu-id="857f3-110">To hide a variable by shadowing it through scope</span></span>  
  
1. <span data-ttu-id="857f3-111">Ermitteln Sie den Bereich definieren die Variable, die Sie ausblenden möchten, und bestimmen Sie einen Unterbereich, in dem sie mit Ihrer Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="857f3-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="857f3-112">Bereich der Variablen</span><span class="sxs-lookup"><span data-stu-id="857f3-112">Variable's region</span></span>|<span data-ttu-id="857f3-113">Zulässiger Teilbereich für ihn neu definieren</span><span class="sxs-lookup"><span data-stu-id="857f3-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="857f3-114">Modul</span><span class="sxs-lookup"><span data-stu-id="857f3-114">Module</span></span>|<span data-ttu-id="857f3-115">Eine Klasse innerhalb des Moduls</span><span class="sxs-lookup"><span data-stu-id="857f3-115">A class within the module</span></span>|  
    |<span data-ttu-id="857f3-116">Klasse</span><span class="sxs-lookup"><span data-stu-id="857f3-116">Class</span></span>|<span data-ttu-id="857f3-117">Eine Unterklasse innerhalb der Klasse</span><span class="sxs-lookup"><span data-stu-id="857f3-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="857f3-118">Eine Prozedur in der Klasse</span><span class="sxs-lookup"><span data-stu-id="857f3-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="857f3-119">Sie können nicht neu definieren, die Variablen in einem Block während dieser Prozedur für eine Prozedur z. B. einer `If`... `End If` Konstruktion oder `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="857f3-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2. <span data-ttu-id="857f3-120">Erstellen des Unterbereichs an, wenn es nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="857f3-120">Create the subregion if it does not already exist.</span></span>  
  
3. <span data-ttu-id="857f3-121">Erstellen Sie innerhalb des Unterbereichs einen [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) die shadowing Variable deklariert.</span><span class="sxs-lookup"><span data-stu-id="857f3-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="857f3-122">Wenn Code innerhalb des Unterbereichs auf den Namen der Variablen verwiesen wird, löst der Compiler den Verweis auf die shadowing-Variable.</span><span class="sxs-lookup"><span data-stu-id="857f3-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="857f3-123">Das folgende Beispiel veranschaulicht die shadowings über den Bereich als auch einen Verweis, der das shadowing umgeht.</span><span class="sxs-lookup"><span data-stu-id="857f3-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="857f3-124">Das vorhergehende Beispiel deklariert die Variable `num` auf Modulebene sowohl auf Prozedurebene (in der Prozedur `show`).</span><span class="sxs-lookup"><span data-stu-id="857f3-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="857f3-125">Die lokale Variable `num` führt Shadowing für die Variable auf Modulebene `num` in `show`, sodass die lokale Variable auf 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="857f3-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="857f3-126">Allerdings besteht keine lokale Variable für das Shadowing `num` in die `useModuleLevelNum` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="857f3-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="857f3-127">Aus diesem Grund `useModuleLevelNum` legt den Wert der Variablen auf Modulebene auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="857f3-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="857f3-128">Die `MsgBox` rufen innerhalb `show` umgeht das Shadowing durch die Qualifizierung `num` mit den Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="857f3-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="857f3-129">Aus diesem Grund wird die Variable auf Modulebene anstelle der lokalen Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="857f3-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="857f3-130">Zu eine Variablen zu verbergen, indem sie durch Vererbung shadowing</span><span class="sxs-lookup"><span data-stu-id="857f3-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1. <span data-ttu-id="857f3-131">Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, in einer Klasse, und klicken Sie auf Klassenebene (außerhalb einer Prozedur) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="857f3-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="857f3-132">Andernfalls kann es nicht durch Vererbung überschatten werden.</span><span class="sxs-lookup"><span data-stu-id="857f3-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2. <span data-ttu-id="857f3-133">Definieren Sie eine Klasse, die von den Wert der Variablen-Klasse abgeleitet werden, wenn Sie noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="857f3-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3. <span data-ttu-id="857f3-134">Schreiben Sie in der abgeleiteten Klasse eine `Dim` Anweisung, die die Variable deklariert.</span><span class="sxs-lookup"><span data-stu-id="857f3-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="857f3-135">Enthalten die [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="857f3-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="857f3-136">Wenn der Code in der abgeleiteten Klasse auf den Namen der Variablen verwiesen wird, löst der Compiler den Verweis auf die Variable an.</span><span class="sxs-lookup"><span data-stu-id="857f3-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="857f3-137">Das folgende Beispiel veranschaulicht die shadowings durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="857f3-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="857f3-138">Es macht zwei Verweise enthalten, von denen eine, die die shadowing Variable zugreift und eine, die das shadowing umgeht.</span><span class="sxs-lookup"><span data-stu-id="857f3-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="857f3-139">Das vorhergehende Beispiel deklariert die Variable `shadowString` in der Basisklasse und in der abgeleiteten Klasse ein Shadowing.</span><span class="sxs-lookup"><span data-stu-id="857f3-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="857f3-140">Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="857f3-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="857f3-141">Es zeigt dann die Variable an bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="857f3-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="857f3-142">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="857f3-142">Robust Programming</span></span>  
 <span data-ttu-id="857f3-143">Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="857f3-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="857f3-144">Die Version, die auf die der Compiler den Verweis löst hängt eine codeanweisung dem Variablennamen verweist, von Faktoren ab, wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="857f3-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="857f3-145">Dies kann das Risiko von Verweisen auf eine unerwünschte Version eine solche Variable erhöhen.</span><span class="sxs-lookup"><span data-stu-id="857f3-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="857f3-146">Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="857f3-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857f3-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="857f3-147">See also</span></span>

- [<span data-ttu-id="857f3-148">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="857f3-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="857f3-149">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="857f3-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="857f3-150">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="857f3-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="857f3-151">Vorgehensweise: Ausblenden einer geerbten Variablen</span><span class="sxs-lookup"><span data-stu-id="857f3-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="857f3-152">Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird</span><span class="sxs-lookup"><span data-stu-id="857f3-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="857f3-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="857f3-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="857f3-154">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="857f3-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="857f3-155">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="857f3-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
