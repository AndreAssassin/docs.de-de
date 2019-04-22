---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821256"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="49dbf-102">Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen (Visual Basic) eine Blockierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="49dbf-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="49dbf-103">Es gibt verschiedenen Fällen bei der es ist wichtig, einem Ereignishandler nicht blockieren nachfolgenden Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="49dbf-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="49dbf-104">Benutzerdefinierte Ereignisse ermöglichen das Ereignis, dessen Ereignishandler asynchron aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="49dbf-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="49dbf-105">Standardmäßig ist das Sicherungsspeicher Feld für eine Ereignisdeklaration ein multicast-Delegat, der seriell auf alle Ereignishandler kombiniert.</span><span class="sxs-lookup"><span data-stu-id="49dbf-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="49dbf-106">Dies bedeutet, dass wenn ein Handler eine lange Zeit in Anspruch nimmt, es anderer Handler blockiert, bis es abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="49dbf-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="49dbf-107">(Gut konzipierte Ereignishandler sollte nie langwierige oder potenziell blockierende Vorgänge ausführen.)</span><span class="sxs-lookup"><span data-stu-id="49dbf-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="49dbf-108">Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet, können Sie ein benutzerdefiniertes Ereignis aus, der die Ereignishandler asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="49dbf-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49dbf-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49dbf-109">Example</span></span>  
 <span data-ttu-id="49dbf-110">In diesem Beispiel die `AddHandler` Accessor fügt der Delegat für jeden Handler des der `Click` Ereignis, um eine <xref:System.Collections.ArrayList> gespeichert, der `EventHandlerList` Feld.</span><span class="sxs-lookup"><span data-stu-id="49dbf-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="49dbf-111">Wenn der code löst die `Click` -Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="49dbf-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="49dbf-112">Diese Methode ruft jede Handler auf einem Arbeitsthread und gibt sofort zurück, sodass Handler gegenseitig blockieren können nicht.</span><span class="sxs-lookup"><span data-stu-id="49dbf-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="49dbf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49dbf-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="49dbf-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="49dbf-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="49dbf-115">Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="49dbf-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
