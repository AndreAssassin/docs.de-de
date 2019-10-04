---
title: Mausereignisse in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: a61f4eedde611cfb7598d55465103924516e06c6
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834600"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="641f4-102">Mausereignisse in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="641f4-102">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="641f4-103">Wenn Sie Mauseingaben behandeln, möchten Sie in der Regel die Position des Mauszeigers und den Zustand der Maustasten kennen.</span><span class="sxs-lookup"><span data-stu-id="641f4-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="641f4-104">Dieses Thema enthält Details zum Abrufen dieser Informationen von Mausereignissen und erörtert die Reihenfolge, in der Mausklickereignisse in Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="641f4-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="641f4-105">Eine Liste und Beschreibung aller Mausereignisse finden Sie unter [How Mouse Input in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="641f4-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="641f4-106">Weitere Informationen finden Sie auch unter [Übersicht über Ereignishandler (Windows Forms)](event-handlers-overview-windows-forms.md) und [Übersicht über Ereignisse (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="641f4-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="641f4-107">Mausinformationen</span><span class="sxs-lookup"><span data-stu-id="641f4-107">Mouse Information</span></span>

<span data-ttu-id="641f4-108">Ein <xref:System.Windows.Forms.MouseEventArgs> wird an Handler von Mausereignissen gesendet, die beim Drücken einer Maustaste und Verfolgen von Mausbewegungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="641f4-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="641f4-109"><xref:System.Windows.Forms.MouseEventArgs> enthält Informationen zum aktuellen Zustand der Maus, z. B. die Position des Mauszeigers in Clientkoordinaten, welche Maustasten gedrückt werden und ob das Mausrad bewegt wurde.</span><span class="sxs-lookup"><span data-stu-id="641f4-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="641f4-110">Zahlreiche Mausereignisse, beispielsweise Ereignisse, die lediglich darüber informieren, dass der Mauszeiger die Grenzen eines Steuerelements überschritten hat, senden ein <xref:System.EventArgs> ohne weitere Informationen an den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="641f4-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="641f4-111">Wenn Sie den aktuellen Zustand der Maustasten oder die Position des Mauszeigers erfahren möchten, ohne ein Mausereignis zu behandeln, können Sie auch die <xref:System.Windows.Forms.Control.MouseButtons%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.MousePosition%2A>-Eigenschaft der <xref:System.Windows.Forms.Control>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="641f4-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="641f4-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> gibt Informationen darüber zurück, welche Maustasten aktuell gedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="641f4-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="641f4-113"><xref:System.Windows.Forms.Control.MousePosition%2A> gibt die Bildschirmkoordinaten des Mauszeigers zurück, was dem von <xref:System.Windows.Forms.Cursor.Position%2A> zurückgegebenen Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="641f4-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="641f4-114">Konvertieren zwischen Bildschirm- und Clientkoordinaten</span><span class="sxs-lookup"><span data-stu-id="641f4-114">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="641f4-115">Da einige Mauspositionsinformationen in Clientkoordinaten und einige in Bildschirmkoordinaten vorhanden sind, müssen Sie möglicherweise einen Punkt aus einem Koordinatensystem in das andere Koordinatensystem konvertieren.</span><span class="sxs-lookup"><span data-stu-id="641f4-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="641f4-116">Eine einfache Möglichkeit hierzu bieten die <xref:System.Windows.Forms.Control.PointToClient%2A>-Methode und die <xref:System.Windows.Forms.Control.PointToScreen%2A>-Methode der <xref:System.Windows.Forms.Control>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="641f4-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="641f4-117">Standardverhalten bei Mausklickereignissen</span><span class="sxs-lookup"><span data-stu-id="641f4-117">Standard Click Event Behavior</span></span>

<span data-ttu-id="641f4-118">Wenn Sie Mausklickereignisse in der richtigen Reihenfolge behandeln möchten, müssen Sie die Reihenfolge kennen, in der Mausklickereignisse in Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="641f4-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="641f4-119">Wenn eine Maustaste gedrückt und wieder losgelassen wird (unabhängig davon, um welche Maustaste es sich handelt), lösen alle Windows Forms-Steuerelemente Mausklickereignisse in derselben Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="641f4-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="641f4-120">In der folgenden Liste ist die Reihenfolge der Ereignisse aufgeführt, die bei einem einzelnen Mausklick ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="641f4-120">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="641f4-121"><xref:System.Windows.Forms.Control.MouseDown> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="641f4-122"><xref:System.Windows.Forms.Control.Click> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="641f4-123"><xref:System.Windows.Forms.Control.MouseClick> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="641f4-124"><xref:System.Windows.Forms.Control.MouseUp> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="641f4-125">Im folgenden finden Sie die Reihenfolge der Ereignisse, die bei einem doppelten Mausklick ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="641f4-125">The following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="641f4-126"><xref:System.Windows.Forms.Control.MouseDown> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="641f4-127"><xref:System.Windows.Forms.Control.Click> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="641f4-128"><xref:System.Windows.Forms.Control.MouseClick> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="641f4-129"><xref:System.Windows.Forms.Control.MouseUp> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="641f4-130"><xref:System.Windows.Forms.Control.MouseDown> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="641f4-131"><xref:System.Windows.Forms.Control.DoubleClick> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="641f4-132">(Dies kann abhängig davon variieren, ob für das betreffende Steuerelement das <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick>-Stilbit auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="641f4-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="641f4-133">Weitere Informationen zum Festlegen eines <xref:System.Windows.Forms.ControlStyles>-Bits finden Sie unter der <xref:System.Windows.Forms.Control.SetStyle%2A>-Methode.)</span><span class="sxs-lookup"><span data-stu-id="641f4-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="641f4-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="641f4-135"><xref:System.Windows.Forms.Control.MouseUp> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="641f4-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="641f4-136">Ein Codebeispiel, das die Reihenfolge der Maus Klick Ereignisse veranschaulicht, finden Sie unter [gewusst wie: Behandeln von Benutzereingabe Ereignissen in Windows Forms-Steuerelementen @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="641f4-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="641f4-137">Einzelne Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="641f4-137">Individual Controls</span></span>

<span data-ttu-id="641f4-138">Die folgenden Steuerelemente weisen nicht das Standardverhalten bei Mausklickereignissen auf:</span><span class="sxs-lookup"><span data-stu-id="641f4-138">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <span data-ttu-id="641f4-139">Für das <xref:System.Windows.Forms.ComboBox>-Steuerelement tritt das im Folgenden beschriebene Verhalten auf, wenn der Benutzer auf das Bearbeitungsfeld, die Schaltfläche oder ein Element in der Liste klickt.</span><span class="sxs-lookup"><span data-stu-id="641f4-139">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="641f4-140">Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-140">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-141">Mit der rechten Maustaste: Es wurden keine Klick Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-141">Right click: No click events raised</span></span>

  - <span data-ttu-id="641f4-142">Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-142">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-143">Doppelklicken Sie mit der rechten Maustaste: Es wurden keine Klick Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-143">Right double-click: No click events raised</span></span>

- <span data-ttu-id="641f4-144"><xref:System.Windows.Forms.TextBox>-Steuerelement, <xref:System.Windows.Forms.RichTextBox>-Steuerelement, <xref:System.Windows.Forms.ListBox>-Steuerelement, <xref:System.Windows.Forms.MaskedTextBox>-Steuerelement und <xref:System.Windows.Forms.CheckedListBox>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="641f4-144"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="641f4-145">Das im Folgenden beschriebene Verhalten tritt auf, wenn der Benutzer innerhalb dieser Steuerelemente auf eine beliebige Stelle klickt.</span><span class="sxs-lookup"><span data-stu-id="641f4-145">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="641f4-146">Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-146">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-147">Mit der rechten Maustaste: Es wurden keine Klick Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-147">Right click: No click events raised</span></span>

  - <span data-ttu-id="641f4-148">Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="641f4-148">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="641f4-149">Doppelklicken Sie mit der rechten Maustaste: Es wurden keine Klick Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-149">Right double-click: No click events raised</span></span>

- <span data-ttu-id="641f4-150"><xref:System.Windows.Forms.ListView>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="641f4-150"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="641f4-151">Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer auf die Elemente im <xref:System.Windows.Forms.ListView>-Steuerelement klickt.</span><span class="sxs-lookup"><span data-stu-id="641f4-151">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="641f4-152">Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-152">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="641f4-153">Neben den weiter unten beschriebenen Ereignissen könnten auch das <xref:System.Windows.Forms.ListView.BeforeLabelEdit>-Ereignis und das <xref:System.Windows.Forms.ListView.AfterLabelEdit>-Ereignis für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.ListView>-Steuerelement durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="641f4-153">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="641f4-154">Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-154">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-155">Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-155">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-156">Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="641f4-156">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="641f4-157">Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="641f4-157">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="641f4-158"><xref:System.Windows.Forms.TreeView>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="641f4-158"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="641f4-159">Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer im <xref:System.Windows.Forms.TreeView>-Steuerelement auf die Elemente selbst oder rechts neben sie klickt.</span><span class="sxs-lookup"><span data-stu-id="641f4-159">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="641f4-160">Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-160">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="641f4-161">Neben den weiter unten beschriebenen Ereignissen könnten auch die Ereignisse <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> und <xref:System.Windows.Forms.TreeView.AfterLabelEdit> für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.TreeView>-Steuerelement durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="641f4-161">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="641f4-162">Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-162">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-163">Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="641f4-163">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="641f4-164">Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="641f4-164">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="641f4-165">Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="641f4-165">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="641f4-166">Zeichen Verhalten beim Umschalten von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="641f4-166">Painting behavior of toggle controls</span></span>

<span data-ttu-id="641f4-167">Umschaltbare Steuerelemente, wie die Steuerelemente, die von der <xref:System.Windows.Forms.ButtonBase>-Klasse abgeleitet werden, weisen bei Mausklickereignissen das folgende Zeichnungsverhalten auf:</span><span class="sxs-lookup"><span data-stu-id="641f4-167">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="641f4-168">Der Benutzer drückt die Maustaste.</span><span class="sxs-lookup"><span data-stu-id="641f4-168">The user presses the mouse button.</span></span>

2. <span data-ttu-id="641f4-169">Das Steuerelement zeichnet im gedrückten Zustand.</span><span class="sxs-lookup"><span data-stu-id="641f4-169">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="641f4-170">Das <xref:System.Windows.Forms.Control.MouseDown>-Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-170">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="641f4-171">Der Benutzer lässt die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="641f4-171">The user releases the mouse button.</span></span>

5. <span data-ttu-id="641f4-172">Das Steuerelement zeichnet im erhöhten Zustand.</span><span class="sxs-lookup"><span data-stu-id="641f4-172">The control paints in the raised state.</span></span>

6. <span data-ttu-id="641f4-173">Das <xref:System.Windows.Forms.Control.Click>-Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-173">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="641f4-174">Das <xref:System.Windows.Forms.Control.MouseClick>-Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-174">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="641f4-175">Das <xref:System.Windows.Forms.Control.MouseUp>-Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="641f4-175">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    > <span data-ttu-id="641f4-176">Wenn der Benutzer den Mauszeiger bei gedrückter Maustaste aus dem umschaltbaren Steuerelement bewegt (z. B. wenn er die Maus bei gedrückter Maustaste vom <xref:System.Windows.Forms.Button>-Steuerelement weg bewegt), zeichnet das umschaltbare Steuerelement im erhöhten Zustand, und es tritt nur das <xref:System.Windows.Forms.Control.MouseUp>-Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="641f4-176">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="641f4-177">Das <xref:System.Windows.Forms.Control.Click>-Ereignis oder das <xref:System.Windows.Forms.Control.MouseClick>-Ereignis tritt in dieser Situation nicht auf.</span><span class="sxs-lookup"><span data-stu-id="641f4-177">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="641f4-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="641f4-178">See also</span></span>

- [<span data-ttu-id="641f4-179">Mauseingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="641f4-179">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
