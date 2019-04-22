---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 828e55e0ddb0382c16c60ae3d9e5958c18e42c10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821335"
---
# <a name="see-visual-basic"></a><span data-ttu-id="1d47f-102">\<finden Sie unter > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d47f-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="1d47f-103">Gibt einen Link zu einem anderen Member an.</span><span class="sxs-lookup"><span data-stu-id="1d47f-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d47f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d47f-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d47f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d47f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="1d47f-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d47f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="1d47f-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1d47f-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="1d47f-108">`member` muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1d47f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d47f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d47f-109">Remarks</span></span>  
 <span data-ttu-id="1d47f-110">Verwenden der `<see>` Tag, um einen Link im Text angegeben.</span><span class="sxs-lookup"><span data-stu-id="1d47f-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="1d47f-111">Verwendung [ \<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) um Text anzugeben, die möglicherweise in einem Abschnitt "Siehe auch" angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1d47f-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="1d47f-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="1d47f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d47f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d47f-113">Example</span></span>  
 <span data-ttu-id="1d47f-114">Dieses Beispiel verwendet die `<see>` -Tag in die `UpdateRecord` Hinweise im Abschnitt zum Verweisen auf die `DoesRecordExist` Methode.</span><span class="sxs-lookup"><span data-stu-id="1d47f-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1d47f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d47f-115">See also</span></span>

- [<span data-ttu-id="1d47f-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="1d47f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
