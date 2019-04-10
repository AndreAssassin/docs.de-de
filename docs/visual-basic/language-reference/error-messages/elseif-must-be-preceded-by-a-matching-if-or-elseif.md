---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 4832fb80cfbe42c7a1303e0de69f36784711c05a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311057"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="5b313-102">"#ElseIf" muss ein entsprechendes "#If" oder "#ElseIf" voranstehen.</span><span class="sxs-lookup"><span data-stu-id="5b313-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
`#ElseIf` <span data-ttu-id="5b313-103">ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="5b313-103">is a conditional compilation directive.</span></span> <span data-ttu-id="5b313-104">Ein `#ElseIf` Klausel muss ein entsprechendes stehen `#If` oder `#ElseIf` Klausel.</span><span class="sxs-lookup"><span data-stu-id="5b313-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="5b313-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="5b313-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b313-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5b313-106">To correct this error</span></span>  
  
1. <span data-ttu-id="5b313-107">Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von dieser getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block für die bedingte Kompilierung oder ein falsch platziertes `#End If`.</span><span class="sxs-lookup"><span data-stu-id="5b313-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="5b313-108">Wenn die `#ElseIf` vorangestellt ist eine `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="5b313-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="5b313-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b313-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b313-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b313-110">See also</span></span>

- [<span data-ttu-id="5b313-111">#If...Then...#Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5b313-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
