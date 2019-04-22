---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7333d4a4d051c157f6732224da0fffe4d7cd35ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827665"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="102ce-102">\<Berechtigung > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="102ce-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="102ce-103">Gibt eine erforderliche Berechtigung für das Element an.</span><span class="sxs-lookup"><span data-stu-id="102ce-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="102ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="102ce-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="102ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="102ce-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="102ce-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="102ce-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="102ce-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="102ce-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="102ce-108">Schließen Sie `member` in Anführungszeichen ("").</span><span class="sxs-lookup"><span data-stu-id="102ce-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="102ce-109">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="102ce-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="102ce-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="102ce-110">Remarks</span></span>  
 <span data-ttu-id="102ce-111">Verwenden der `<permission>` Tag, um den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="102ce-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="102ce-112">Verwenden der <xref:System.Security.PermissionSet> Klasse, um den Zugriff auf ein Element anzugeben.</span><span class="sxs-lookup"><span data-stu-id="102ce-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="102ce-113">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="102ce-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="102ce-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="102ce-114">Example</span></span>  
 <span data-ttu-id="102ce-115">Dieses Beispiel verwendet die `<permission>` Tag beschrieben, dass die <xref:System.Security.Permissions.FileIOPermission> erforderlich ist der `ReadFile` Methode.</span><span class="sxs-lookup"><span data-stu-id="102ce-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="102ce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="102ce-116">See also</span></span>

- [<span data-ttu-id="102ce-117">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="102ce-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
