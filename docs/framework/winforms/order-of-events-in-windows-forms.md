---
title: Ereignisreihenfolge in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: 28eb451c7edd740664f80f8ec35c60192764043c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949875"
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="7e6d1-102">Ereignisreihenfolge in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6d1-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="7e6d1-103">Die Reihenfolge, in der Ereignisse in Windows Forms-Anwendungen ausgelöst werden, ist für Entwickler von besonderem Interesse, die sich mit der sukzessiven Verarbeitung jedes dieser Ereignisse befassen müssen.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="7e6d1-104">Wenn eine Situation die sorgfältige Verarbeitung von Ereignissen erfordert, z. B. beim Neuzeichnen von Komponenten des Formulars, ist ein Bewusstsein für die genaue Reihenfolge, in der Ereignisse zur Laufzeit ausgelöst werden, geboten.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="7e6d1-105">Dieses Thema enthält Details zur Reihenfolge von Ereignissen im Verlauf einiger wichtiger Phasen der Lebensdauer von Anwendungen und Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="7e6d1-106">Spezifische Details zur Reihenfolge der Mauseingabe Ereignisse finden Sie unter [Mausereignisse in Windows Forms](mouse-events-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7e6d1-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="7e6d1-107">Eine Übersicht über die Ereignisse in Windows Forms finden Sie unter [Übersicht über Ereignisse](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7e6d1-107">For an overview of events in Windows Forms, see [Events Overview](events-overview-windows-forms.md).</span></span> <span data-ttu-id="7e6d1-108">Ausführliche Informationen über die Zusammensetzung von Ereignis Handlern finden Sie unter [Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7e6d1-108">For details about the makeup of event handlers, see [Event Handlers Overview](event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="7e6d1-109">Ereignisse beim Starten und Herunterfahren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7e6d1-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="7e6d1-110">Die Klassen <xref:System.Windows.Forms.Form> und <xref:System.Windows.Forms.Control> stellen einen Satz von Ereignissen bereit, die sich auf das Starten und Herunterfahren von Anwendungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="7e6d1-111">Beim Starten einer Windows Forms-Anwendung werden die Startereignisse des Hauptformulars in der folgenden Reihenfolge ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="7e6d1-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="7e6d1-112">Beim Schließen einer Windows Forms-Anwendung werden die Ereignisse des Hauptformulars zum Herunterfahren in der folgenden Reihenfolge ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="7e6d1-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="7e6d1-113">Das <xref:System.Windows.Forms.Application.ApplicationExit>-Ereignis der <xref:System.Windows.Forms.Application>-Klasse wird nach den Ereignissen des Hauptformulars zum Herunterfahren ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e6d1-114">Visual Basic 2005 stellt zusätzliche Anwendungsereignisse bereit, z. B. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e6d1-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="7e6d1-115">Fokusereignisse und Validierungsereignisse</span><span class="sxs-lookup"><span data-stu-id="7e6d1-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="7e6d1-116">Wenn Sie den Fokus über die Tastatur ändern (TAB, UMSCHALT+TAB usw.), indem Sie die Methoden <xref:System.Windows.Forms.Control.Select%2A> oder <xref:System.Windows.Forms.Control.SelectNextControl%2A> aufrufen oder die <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A>-Eigenschaft auf das aktuelle Formular festlegen, treten die Fokusereignisse der <xref:System.Windows.Forms.Control>-Klasse in der folgenden Reihenfolge auf:</span><span class="sxs-lookup"><span data-stu-id="7e6d1-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="7e6d1-117">Wenn Sie den Fokus über die Maus oder durch Aufrufen der <xref:System.Windows.Forms.Control.Focus%2A>-Methode ändern, treten die Fokusereignisse der <xref:System.Windows.Forms.Control>-Klasse in der folgenden Reihenfolge auf:</span><span class="sxs-lookup"><span data-stu-id="7e6d1-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="7e6d1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e6d1-118">See also</span></span>

- [<span data-ttu-id="7e6d1-119">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6d1-119">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
