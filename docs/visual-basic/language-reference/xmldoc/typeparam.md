---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 014623be84f9d7eb8a25ac4aadcce450f158c154
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827236"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="5791b-102">\<Typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5791b-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="5791b-103">Definiert einen Typparametername und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="5791b-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5791b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5791b-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5791b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5791b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5791b-106">Der Name des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="5791b-106">The name of the type parameter.</span></span> <span data-ttu-id="5791b-107">Setzen Sie den Namen in einfache oder doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="5791b-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="5791b-108">Eine Beschreibung des Typparameters.</span><span class="sxs-lookup"><span data-stu-id="5791b-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5791b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5791b-109">Remarks</span></span>  
 <span data-ttu-id="5791b-110">Verwenden der `<typeparam>` Tag im Kommentar für einen generischen Typ oder generische Memberdeklaration, um einen der Typparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="5791b-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="5791b-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="5791b-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5791b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5791b-112">Example</span></span>  
 <span data-ttu-id="5791b-113">Dieses Beispiel verwendet die `<typeparam>` Tag zum Beschreiben der `id` Parameter.</span><span class="sxs-lookup"><span data-stu-id="5791b-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="5791b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5791b-114">See also</span></span>

- [<span data-ttu-id="5791b-115">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="5791b-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
