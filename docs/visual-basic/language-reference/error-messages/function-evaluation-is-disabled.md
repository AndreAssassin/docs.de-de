---
title: Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801945"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="7a829-102">Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="7a829-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="7a829-103">Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat. Wenn Sie die Funktionsauswertung wieder aktivieren möchten, starten Sie den Einzelschrittdurchlauf oder das Debuggen erneut</span><span class="sxs-lookup"><span data-stu-id="7a829-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="7a829-104">Im Visual Studio-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="7a829-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="7a829-105">Mögliche Ursachen für den Aufruf einer Prozedur zu einem Timeout sind eine Endlosschleife oder *Endlosschleife*.</span><span class="sxs-lookup"><span data-stu-id="7a829-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="7a829-106">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7a829-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="7a829-107">Ist eine besondere Variante einer Endlosschleife *Rekursion*.</span><span class="sxs-lookup"><span data-stu-id="7a829-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="7a829-108">Weitere Informationen finden Sie unter [rekursive Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7a829-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="7a829-109">**Fehler-ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="7a829-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a829-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7a829-110">To correct this error</span></span>  
  
1. <span data-ttu-id="7a829-111">Bestimmen Sie nach Möglichkeit die vorherige Funktionsevaluierung und die Ursache für das Timeout. Andernfalls kann dieser Fehler erneut auftreten.</span><span class="sxs-lookup"><span data-stu-id="7a829-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="7a829-112">Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.</span><span class="sxs-lookup"><span data-stu-id="7a829-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a829-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a829-113">See also</span></span>

- [<span data-ttu-id="7a829-114">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a829-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="7a829-115">Navigieren im Code mit dem Debugger</span><span class="sxs-lookup"><span data-stu-id="7a829-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
