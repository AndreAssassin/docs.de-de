---
title: RemoveHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 8a9dc5874629c1687318496bd7c4016eb318c25a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831682"
---
# <a name="removehandler-statement"></a><span data-ttu-id="e2130-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2130-102">RemoveHandler Statement</span></span>
<span data-ttu-id="e2130-103">Entfernt die Zuordnung zwischen einem Ereignis und einen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e2130-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2130-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2130-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e2130-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e2130-105">Parts</span></span>  
  
|<span data-ttu-id="e2130-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e2130-106">Term</span></span>|<span data-ttu-id="e2130-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e2130-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="e2130-108">Der Name des behandelten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e2130-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="e2130-109">Der Name der Prozedur zurzeit verarbeitet das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e2130-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2130-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2130-110">Remarks</span></span>  
 <span data-ttu-id="e2130-111">Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der programmausführung.</span><span class="sxs-lookup"><span data-stu-id="e2130-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2130-112">Für benutzerdefinierte Ereignisse die `RemoveHandler` -Anweisung ruft des Ereignisses `RemoveHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="e2130-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="e2130-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e2130-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2130-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2130-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e2130-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2130-115">See also</span></span>

- [<span data-ttu-id="e2130-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2130-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="e2130-117">Handles</span><span class="sxs-lookup"><span data-stu-id="e2130-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="e2130-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2130-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e2130-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e2130-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
