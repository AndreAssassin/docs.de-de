---
title: <value> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 09577d931c6b1f571cd4112c788da38bab85bf42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523278"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="c5c7f-102">\<value> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c5c7f-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c5c7f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5c7f-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5c7f-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5c7f-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="c5c7f-105">Eine Beschreibung der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c5c7f-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5c7f-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c5c7f-106">Remarks</span></span>  
 <span data-ttu-id="c5c7f-107">Mit dem \<value>-Tag können Sie den Wert beschreiben, den eine Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="c5c7f-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="c5c7f-108">Beachten Sie, dass beim Hinzufügen einer Eigenschaft mithilfe des Code-Assistenten in der Entwicklungsumgebung von Visual Studio .NET der neuen Eigenschaft ein [\<summary>](./summary.md)-Tag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c5c7f-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="c5c7f-109">Sie sollten dann manuell ein \<value>-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="c5c7f-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="c5c7f-110">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c5c7f-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5c7f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5c7f-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="c5c7f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5c7f-112">See also</span></span>

- [<span data-ttu-id="c5c7f-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c5c7f-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c5c7f-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="c5c7f-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
