---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 41b7ef1f435fd0a4f20c4ca2936e2d91e155f7c5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347424"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="2fcb6-102">Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fcb6-102">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="2fcb6-103">This example shows how to add XML documentation comments to your code.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-103">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="2fcb6-104">To create XML documentation for a type or member</span><span class="sxs-lookup"><span data-stu-id="2fcb6-104">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="2fcb6-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="2fcb6-106">Type `'''` (three single-quotation marks).</span><span class="sxs-lookup"><span data-stu-id="2fcb6-106">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="2fcb6-107">An XML skeleton for the type or member is added in the **Code Editor**.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="2fcb6-108">Add descriptive information between the appropriate tags.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-108">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fcb6-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="2fcb6-110">Add additional code that uses the type or member with the new XML documentation comments.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="2fcb6-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="2fcb6-112">Compile the code to generate an XML file containing the documentation comments.</span><span class="sxs-lookup"><span data-stu-id="2fcb6-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="2fcb6-113">Weitere Informationen finden Sie unter [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="2fcb6-113">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fcb6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fcb6-114">See also</span></span>

- [<span data-ttu-id="2fcb6-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="2fcb6-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="2fcb6-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="2fcb6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="2fcb6-117">-doc</span><span class="sxs-lookup"><span data-stu-id="2fcb6-117">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
