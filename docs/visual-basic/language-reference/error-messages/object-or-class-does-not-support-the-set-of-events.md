---
title: Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342881"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="a88e1-102">Das Objekt oder die Klasse unterstützt diese Gruppe von Ereignissen nicht.</span><span class="sxs-lookup"><span data-stu-id="a88e1-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="a88e1-103">Sie haben versucht, Sie verwenden eine `WithEvents` Variable mit dem eine Komponente, die als Ereignisquelle für den angegebenen Satz von Ereignissen nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a88e1-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="a88e1-104">Beispielsweise die Senke Ereignisse eines Objekts, und klicken Sie dann ein anderes Objekt zu erstellen, möchten `Implements` das erste Objekt.</span><span class="sxs-lookup"><span data-stu-id="a88e1-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="a88e1-105">Obwohl Sie denken, dass Sie Ereignisse aus dem implementierte Objekt auffangen können vielleicht, ist dies nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="a88e1-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="a88e1-106">`Implements` nur implementiert eine Schnittstelle für Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a88e1-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="a88e1-107">`WithEvents` wird nicht unterstützt, für die Private `UserControls`, da die Typinformationen zum Auslösen der `ObjectEvent` zur Laufzeit nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a88e1-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a88e1-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a88e1-108">To correct this error</span></span>  
  
1. <span data-ttu-id="a88e1-109">Sie können nicht für eine Komponente Auffangen von Ereignissen, die keine Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="a88e1-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88e1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a88e1-110">See also</span></span>

- [<span data-ttu-id="a88e1-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="a88e1-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="a88e1-112">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a88e1-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
