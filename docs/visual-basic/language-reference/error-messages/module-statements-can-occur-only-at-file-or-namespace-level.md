---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592098"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="aafd7-102">Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aafd7-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="aafd7-103">`Module` -Anweisungen müssen am Anfang der Quelldatei angezeigt werden unmittelbar nach `Option` und `Imports` Anweisungen, globalen Attributen und Namespacedeklarationen, aber vor allen anderen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="aafd7-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="aafd7-104">**Fehler-ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="aafd7-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aafd7-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="aafd7-105">To correct this error</span></span>  
  
- <span data-ttu-id="aafd7-106">Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="aafd7-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aafd7-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aafd7-107">See also</span></span>

- [<span data-ttu-id="aafd7-108">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aafd7-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
