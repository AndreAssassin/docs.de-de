---
title: 'Vorgehensweise: Erstellen einer Windows Forms-Anwendung über die Befehlszeile'
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: af1548602ece8ea0f5720a836ec05648854e198f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127247"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="7d214-102">Vorgehensweise: Erstellen einer Windows Forms-Anwendung über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="7d214-102">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="7d214-103">In den folgenden Verfahren werden die grundlegenden Schritte beschrieben, die Sie zum Erstellen einer Windows Forms-Anwendung und Ausführen dieser Anwendung über die Befehlszeile abschließen müssen.</span><span class="sxs-lookup"><span data-stu-id="7d214-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="7d214-104">Visual Studio bietet umfassende Unterstützung für diese Verfahren.</span><span class="sxs-lookup"><span data-stu-id="7d214-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="7d214-105">Siehe auch Exemplarische Vorgehensweise [: Hosting eines Windows Forms-Steuer Elements in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="7d214-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="7d214-106">Prozedur</span><span class="sxs-lookup"><span data-stu-id="7d214-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="7d214-107">So erstellen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="7d214-107">To create the form</span></span>  
  
1. <span data-ttu-id="7d214-108">Geben Sie in einer leeren Codedatei die folgenden `Imports`-oder `using`-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="7d214-108">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="7d214-109">Deklarieren Sie eine Klasse mit dem Namen `Form1`, die von der Formular Klasse erbt:</span><span class="sxs-lookup"><span data-stu-id="7d214-109">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="7d214-110">Erstellen Sie einen Parameter losen Konstruktor für `Form1`.</span><span class="sxs-lookup"><span data-stu-id="7d214-110">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="7d214-111">In einem späteren Verfahren fügen Sie dem Konstruktor weiteren Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d214-111">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="7d214-112">Fügen Sie der Klasse eine `Main`-Method hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d214-112">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="7d214-113">Wenden Sie die <xref:System.STAThreadAttribute> auf C# die `Main` Methode an, um anzugeben, dass die Windows Forms Anwendung ein Single Thread-Apartment ist.</span><span class="sxs-lookup"><span data-stu-id="7d214-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="7d214-114">(Das-Attribut ist in Visual Basic nicht erforderlich, da Windows Forms-Anwendungen, die mit Visual Basic entwickelt wurden, standardmäßig ein Single Thread-Apartment Modell verwenden.)</span><span class="sxs-lookup"><span data-stu-id="7d214-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="7d214-115">Wenden Sie <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> an, um Betriebssystem Stile auf Ihre Anwendung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7d214-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="7d214-116">Erstellen Sie eine Instanz des Formulars, und führen Sie diese aus.</span><span class="sxs-lookup"><span data-stu-id="7d214-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="7d214-117">So kompilieren Sie die Anwendung und führen sie aus</span><span class="sxs-lookup"><span data-stu-id="7d214-117">To compile and run the application</span></span>  
  
1. <span data-ttu-id="7d214-118">Navigieren Sie an der .NET Framework-Eingabeaufforderung zu dem Verzeichnis, in dem Sie die `Form1`-Klasse erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7d214-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="7d214-119">Kompilieren Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="7d214-119">Compile the form.</span></span>  
  
    - <span data-ttu-id="7d214-120">Wenn Sie verwenden C#, geben Sie Folgendes ein: `csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="7d214-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="7d214-121">Wenn Sie Visual Basic verwenden, geben Sie Folgendes ein: `vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="7d214-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="7d214-122">Geben Sie an der Eingabeaufforderung Folgendes ein: `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="7d214-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="7d214-123">Hinzufügen eines Steuer Elements und behandeln eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7d214-123">Adding a control and handling an event</span></span>

<span data-ttu-id="7d214-124">Anhand der vorherigen Schritte wurde veranschaulicht, wie Sie ein einfaches Windows Form erstellen, das kompiliert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d214-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="7d214-125">Im nächsten Verfahren wird erläutert, wie Sie ein Steuerelement erstellen und es dem Formular hinzufügen und wie Sie ein Ereignis für das Steuerelement behandeln.</span><span class="sxs-lookup"><span data-stu-id="7d214-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="7d214-126">Weitere Informationen zu den Steuerelementen, die Sie Windows Forms hinzufügen können, finden Sie unter Windows Forms-Steuer [Elemente](./controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d214-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="7d214-127">Zusätzlich zu dem Wissen, wie Windows Forms-Anwendungen erstellt werden, sollten Sie auch wissen, wie ereignisbasierte Programmierung geht und wie Benutzereingaben behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="7d214-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="7d214-128">Weitere Informationen finden Sie unter [Erstellen von Ereignis Handlern in Windows Forms](creating-event-handlers-in-windows-forms.md)und [Behandeln von Benutzereingaben](./controls/handling-user-input.md) .</span><span class="sxs-lookup"><span data-stu-id="7d214-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="7d214-129">So deklarieren Sie ein Button-Steuerelement und behandeln sein Click-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7d214-129">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="7d214-130">Deklarieren Sie ein Button-Steuerelement namens `button1`.</span><span class="sxs-lookup"><span data-stu-id="7d214-130">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="7d214-131">Erstellen Sie im Konstruktor die Schaltfläche, und legen Sie deren Eigenschaften <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Text%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="7d214-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="7d214-132">Fügen Sie die Schaltfläche dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d214-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="7d214-133">Im folgenden Codebeispiel wird veranschaulicht, wie Sie das Schaltflächen-Steuerelement deklarieren:</span><span class="sxs-lookup"><span data-stu-id="7d214-133">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="7d214-134">Erstellen Sie eine Methode, um das <xref:System.Windows.Forms.Control.Click>-Ereignis für die Schaltfläche zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="7d214-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="7d214-135">Zeigen Sie im Click-Ereignishandler eine <xref:System.Windows.Forms.MessageBox>-Instanz mit der Meldung "Hello World" an.</span><span class="sxs-lookup"><span data-stu-id="7d214-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="7d214-136">Im folgenden Codebeispiel wird veranschaulicht, wie das Click-Ereignis des Button-Steuer Elements behandelt wird:</span><span class="sxs-lookup"><span data-stu-id="7d214-136">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="7d214-137">Ordnen Sie das <xref:System.Windows.Forms.Control.Click>-Ereignis der Methode zu, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7d214-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="7d214-138">Im folgenden Codebeispiel wird veranschaulicht, wie der Methode das Ereignis zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="7d214-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="7d214-139">Kompilieren Sie die Anwendung, und führen Sie sie aus, wie im vorherigen Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d214-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d214-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d214-140">Example</span></span>  
 
<span data-ttu-id="7d214-141">Das folgende Codebeispiel ist das komplette Beispiel aus den vorherigen Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="7d214-141">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7d214-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d214-142">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="7d214-143">Ändern der Darstellung von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d214-143">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="7d214-144">Erweitern von Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7d214-144">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="7d214-145">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d214-145">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
