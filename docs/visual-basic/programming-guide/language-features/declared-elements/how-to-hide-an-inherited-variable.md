---
title: 'Vorgehensweise: Ausblenden einer geerbten Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: ee147ecd00b88b538ace32844c42ac9c5022b2ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331701"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="dbe46-102">Vorgehensweise: Ausblenden einer geerbten Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbe46-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="dbe46-103">Eine abgeleitete Klasse erbt alle Definitionen der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="dbe46-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="dbe46-104">Wenn Sie eine Variable mit dem gleichen Namen wie ein Element der Basisklasse definieren möchten, können Sie ausblenden, oder *Schatten*, das Basisklasse-Element, wenn Sie die Variable in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="dbe46-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="dbe46-105">Wenn Sie dies tun, greift Code in der abgeleiteten Klasse die Variable auf, es sei denn, sie explizit das Shadowing umgeht.</span><span class="sxs-lookup"><span data-stu-id="dbe46-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="dbe46-106">Ein weiterer Grund dafür, dass Sie eine geerbte Variablen ausblenden möchten, ist zum Schutz vor Basisklasse Revision.</span><span class="sxs-lookup"><span data-stu-id="dbe46-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="dbe46-107">Die Basisklasse kann eine Änderung durchlaufen, die das Element ändert, von denen, das Sie erbt, sind.</span><span class="sxs-lookup"><span data-stu-id="dbe46-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="dbe46-108">In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise in die abgeleitete Klasse, die in die Variable nicht auf das Element der Basisklasse aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="dbe46-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="dbe46-109">Ausblenden eine geerbte Variablen</span><span class="sxs-lookup"><span data-stu-id="dbe46-109">To hide an inherited variable</span></span>  
  
1. <span data-ttu-id="dbe46-110">Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, die auf Klassenebene (außerhalb einer Prozedur) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="dbe46-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="dbe46-111">Andernfalls müssen Sie nicht ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="dbe46-111">Otherwise you do not need to hide it.</span></span>  
  
2. <span data-ttu-id="dbe46-112">Schreiben Sie in der abgeleiteten Klasse eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) deklarieren Ihrer Variablen.</span><span class="sxs-lookup"><span data-stu-id="dbe46-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="dbe46-113">Verwenden Sie den gleichen Namen wie die geerbten Variablen.</span><span class="sxs-lookup"><span data-stu-id="dbe46-113">Use the same name as that of the inherited variable.</span></span>  
  
3. <span data-ttu-id="dbe46-114">Enthalten die [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="dbe46-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="dbe46-115">Wenn der Code in der abgeleiteten Klasse auf den Namen der Variablen verwiesen wird, löst der Compiler den Verweis auf die Variable an.</span><span class="sxs-lookup"><span data-stu-id="dbe46-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="dbe46-116">Das folgende Beispiel veranschaulicht das shadowing einer geerbten Variablen.</span><span class="sxs-lookup"><span data-stu-id="dbe46-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
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
  
     <span data-ttu-id="dbe46-117">Das vorhergehende Beispiel deklariert die Variable `shadowString` in der Basisklasse und in der abgeleiteten Klasse ein Shadowing.</span><span class="sxs-lookup"><span data-stu-id="dbe46-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="dbe46-118">Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="dbe46-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="dbe46-119">Es zeigt dann die Variable an bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dbe46-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dbe46-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="dbe46-120">Robust Programming</span></span>  
 <span data-ttu-id="dbe46-121">Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="dbe46-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="dbe46-122">Die Version, die auf die der Compiler den Verweis löst hängt eine codeanweisung dem Variablennamen verweist, von Faktoren ab, wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="dbe46-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="dbe46-123">Dies kann das Risiko von Verweisen auf eine unerwünschte Version eine solche Variable erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dbe46-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="dbe46-124">Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="dbe46-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe46-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbe46-125">See also</span></span>

- [<span data-ttu-id="dbe46-126">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="dbe46-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="dbe46-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbe46-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="dbe46-128">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="dbe46-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="dbe46-129">Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable</span><span class="sxs-lookup"><span data-stu-id="dbe46-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="dbe46-130">Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird</span><span class="sxs-lookup"><span data-stu-id="dbe46-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="dbe46-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="dbe46-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="dbe46-132">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="dbe46-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="dbe46-133">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="dbe46-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
