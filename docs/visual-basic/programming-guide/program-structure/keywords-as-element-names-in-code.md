---
title: Schlüsselwörter als Elementnamen in Code (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841146"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="1eb46-102">Schlüsselwörter als Elementnamen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eb46-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="1eb46-103">Jedem Programmelement, z. B. eine Variable, eine Klasse oder ein Member, haben den gleichen Namen wie ein eingeschränktes Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1eb46-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="1eb46-104">Sie können z. B. erstellen eine Variablen namens `Loop`.</span><span class="sxs-lookup"><span data-stu-id="1eb46-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="1eb46-105">Allerdings zum Verweisen auf Ihre Version des Zertifikats – das hat des gleichen Namens wie die eingeschränkte `Loop` Schlüsselwort – müssen Sie ein vollständiger Qualifizierungspfad voranstellen oder schließen Sie ihn in eckige Klammern (`[ ]`), wie im folgende Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1eb46-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="1eb46-106">Wenn Sie nicht tun, eines dieser, Visual Basic wird für die systeminterne Funktion `Loop` Schlüsselwort und erzeugt einen Fehler, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1eb46-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="1eb46-107">Eckige Klammern können beim Verweisen auf die Formulare und Steuerelemente, und wenn eine Variable deklarieren oder definieren eine Prozedur mit dem gleichen Namen wie ein eingeschränktes Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1eb46-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="1eb46-108">Es kann leicht vergessen, qualifizierte Namen oder eckige Klammern einschließen und daher Fehler in Ihren Code einführen und machen es schwieriger zu lesen sein.</span><span class="sxs-lookup"><span data-stu-id="1eb46-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="1eb46-109">Aus diesem Grund empfehlen wir, dass Sie eingeschränkte Schlüsselwörter nicht als die Namen der Programmelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eb46-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="1eb46-110">Allerdings eine zukünftige Version von Visual Basic einem neuen Schlüsselwort, verursacht einen Konflikt mit vorhandenen Steuerelementnamen eines Formulars oder definiert, können klicken Sie dann dieses Verfahren Sie beim Aktualisieren von Code mit der neuen Version funktioniert.</span><span class="sxs-lookup"><span data-stu-id="1eb46-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eb46-111">Das Programm kann auch Elementnamen bereitgestellt, die von anderen referenzierten Assemblys enthalten.</span><span class="sxs-lookup"><span data-stu-id="1eb46-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="1eb46-112">Diese Namen mit beschränkter Schlüsselwörter in Konflikt stehen, bewirkt, dass dann platzieren eckige Klammern sie Visual Basic, um sie als die definierte Elemente interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1eb46-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb46-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb46-113">See also</span></span>

- [<span data-ttu-id="1eb46-114">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="1eb46-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="1eb46-115">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="1eb46-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="1eb46-116">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1eb46-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
