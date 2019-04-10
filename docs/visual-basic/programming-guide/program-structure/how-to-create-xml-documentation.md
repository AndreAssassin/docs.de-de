---
title: 'Vorgehensweise: Erstellen von XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 95f6c5b23deadc16eb1e81f274e2cc5149598fb7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294483"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="60f9d-102">Vorgehensweise: Erstellen von XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60f9d-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="60f9d-103">Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare zu Ihrem Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60f9d-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="60f9d-104">Um XML-Dokumentation für einen Typ oder Member zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60f9d-104">To create XML documentation for a type or member</span></span>  
  
1. <span data-ttu-id="60f9d-105">In der **Code-Editor**, positionieren Sie den Cursor in die Zeile über den Typ oder Member, für die Erstellung der Dokumentation werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60f9d-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2. <span data-ttu-id="60f9d-106">Typ `'''` (drei einfache Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="60f9d-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="60f9d-107">Ein XML-Gerüst für den Typ oder Member hinzugefügt wird, die **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="60f9d-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3. <span data-ttu-id="60f9d-108">Hinzufügen von beschreibenden Informationen zwischen den entsprechenden Tags.</span><span class="sxs-lookup"><span data-stu-id="60f9d-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60f9d-109">Wenn Sie zusätzliche Zeilen innerhalb des Blocks des XML-Dokumentation hinzufügen, muss jede Zeile mit beginnen `'''`.</span><span class="sxs-lookup"><span data-stu-id="60f9d-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4. <span data-ttu-id="60f9d-110">Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentaren verwendet.</span><span class="sxs-lookup"><span data-stu-id="60f9d-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="60f9d-111">IntelliSense zeigt den Text aus der \<summary >-Tag für den Typ oder Member.</span><span class="sxs-lookup"><span data-stu-id="60f9d-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5. <span data-ttu-id="60f9d-112">Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="60f9d-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="60f9d-113">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="60f9d-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f9d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60f9d-114">See also</span></span>

- [<span data-ttu-id="60f9d-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="60f9d-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="60f9d-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="60f9d-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="60f9d-117">/doc</span><span class="sxs-lookup"><span data-stu-id="60f9d-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
