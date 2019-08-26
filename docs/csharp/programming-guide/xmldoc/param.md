---
title: <param> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: e2e9bd4478ceaf2f491aba0aa3db8bae7857f28d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587927"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="4b8c1-102">\<param> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4b8c1-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4b8c1-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b8c1-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b8c1-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b8c1-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4b8c1-105">Der Name eines Methodenparameters.</span><span class="sxs-lookup"><span data-stu-id="4b8c1-105">The name of a method parameter.</span></span> <span data-ttu-id="4b8c1-106">Setzen Sie den Namen in doppelte Anführungszeichen (" ").</span><span class="sxs-lookup"><span data-stu-id="4b8c1-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="4b8c1-107">Eine Beschreibung für den Parameter</span><span class="sxs-lookup"><span data-stu-id="4b8c1-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b8c1-108">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="4b8c1-108">Remarks</span></span>  
 <span data-ttu-id="4b8c1-109">Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4b8c1-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="4b8c1-110">Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param>-Tags.</span><span class="sxs-lookup"><span data-stu-id="4b8c1-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="4b8c1-111">Der Text für den \<param>-Tag wird in IntelliSense, dem Objektkatalog, und im Webbericht für Codekommentare angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b8c1-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="4b8c1-112">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4b8c1-112">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b8c1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b8c1-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b8c1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b8c1-114">See also</span></span>

- [<span data-ttu-id="4b8c1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4b8c1-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4b8c1-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="4b8c1-116">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
