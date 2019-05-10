---
title: 'Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 4d2290622e648030f150d9bb06ce1f3000145759
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211470"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="7fc73-102">Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7fc73-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="7fc73-103">Zusätzlich zum Erstellen von Ereignissen, die mit der Windows Forms-Designer in Visual Studio, können Sie auch einen Ereignishandler zur Laufzeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="7fc73-103">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="7fc73-104">Durch diese Aktion können Sie Ereignishandler basierend auf Bedingungen in Code zur Laufzeit miteinander verknüpfen, statt sie beim ersten Start des Programms miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="7fc73-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="7fc73-105">Erstellen Sie einen Ereignishandler zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7fc73-105">Create an event handler at run time</span></span>

1. <span data-ttu-id="7fc73-106">Öffnen Sie das Formular, dem einen Ereignishandler hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7fc73-106">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="7fc73-107">Fügen Sie eine Methode zu Ihrem Formular hinzu. Verwenden Sie hierfür die Methodensignatur für das Ereignis, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7fc73-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="7fc73-108">Angenommen, Sie bearbeiten die <xref:System.Windows.Forms.Control.Click> Ereignis eine <xref:System.Windows.Forms.Button> -Steuerelement, erstellen Sie eine Methode z. B. Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7fc73-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. <span data-ttu-id="7fc73-109">Fügen Sie für Ihre Anwendung geeigneten Code zum Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="7fc73-109">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="7fc73-110">Bestimmen Sie, für welches Formular oder Steuerelement Sie einen Ereignishandler erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7fc73-110">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="7fc73-111">Fügen Sie in einer Methode innerhalb der Formularklasse einen Code hinzu, der den zu bearbeitenden Ereignishandler angibt.</span><span class="sxs-lookup"><span data-stu-id="7fc73-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="7fc73-112">Der folgende Code gibt beispielsweise den Ereignishandler `button1_Click` Handles der <xref:System.Windows.Forms.Control.Click> Ereignis eine <xref:System.Windows.Forms.Button> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="7fc73-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="7fc73-113">Die <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> -Methode in der oben genannten Visual Basic-Code wird einen Click-Ereignishandler für die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="7fc73-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fc73-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fc73-114">See also</span></span>

- [<span data-ttu-id="7fc73-115">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fc73-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="7fc73-116">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="7fc73-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="7fc73-117">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fc73-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
