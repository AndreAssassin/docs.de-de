---
title: AddHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004545"
---
# <a name="addhandler-statement"></a><span data-ttu-id="e1951-102">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e1951-102">AddHandler Statement</span></span>
<span data-ttu-id="e1951-103">Ordnet ein Ereignis einem Ereignishandler zur Laufzeit zu.</span><span class="sxs-lookup"><span data-stu-id="e1951-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1951-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1951-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e1951-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e1951-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="e1951-106">event</span><span class="sxs-lookup"><span data-stu-id="e1951-106">event</span></span>|<span data-ttu-id="e1951-107">Der Name des zu behandelnden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e1951-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="e1951-108">Der Name einer Prozedur, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="e1951-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="e1951-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1951-109">Remarks</span></span>  
 <span data-ttu-id="e1951-110">Die Anweisungen `AddHandler` und `RemoveHandler` ermöglichen das Starten und Abbrechen der Ereignis Behandlung während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="e1951-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="e1951-111">Die Signatur der `eventhandler`-Prozedur muss mit der Signatur des Ereignisses `event` identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e1951-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="e1951-112">Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="e1951-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="e1951-113">Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="e1951-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="e1951-114">Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e1951-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="e1951-115">Weitere Informationen finden Sie unter [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e1951-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1951-116">Für benutzerdefinierte Ereignisse ruft die `AddHandler`-Anweisung den `AddHandler`-Accessor des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="e1951-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="e1951-117">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e1951-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1951-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1951-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e1951-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1951-119">See also</span></span>

- [<span data-ttu-id="e1951-120">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e1951-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="e1951-121">Handles</span><span class="sxs-lookup"><span data-stu-id="e1951-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="e1951-122">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e1951-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e1951-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e1951-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
