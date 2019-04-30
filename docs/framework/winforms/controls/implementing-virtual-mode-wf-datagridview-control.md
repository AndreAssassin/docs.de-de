---
title: 'Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973770"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="398a0-102">Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="398a0-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="398a0-103">Bei sehr große Mengen von Tabellendaten in angezeigt werden soll eine <xref:System.Windows.Forms.DataGridView> -Steuerelements legen Sie die <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> Eigenschaft `true` und explizit die Interaktion mit dem Datenspeicher des Steuerelements verwalten.</span><span class="sxs-lookup"><span data-stu-id="398a0-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="398a0-104">Dadurch können Sie die Leistung des Steuerelements in diesem Fall optimieren.</span><span class="sxs-lookup"><span data-stu-id="398a0-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="398a0-105">Die <xref:System.Windows.Forms.DataGridView> Steuerelement bietet mehrere Ereignisse, die Sie behandeln können, für die Interaktion mit einem benutzerdefinierten Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="398a0-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="398a0-106">Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Implementierung von diesen Ereignishandlern.</span><span class="sxs-lookup"><span data-stu-id="398a0-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="398a0-107">Das Codebeispiel in diesem Thema wird eine sehr einfache Datenquelle zur Veranschaulichung verwendet.</span><span class="sxs-lookup"><span data-stu-id="398a0-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="398a0-108">In einer produktionsumgebung werden Sie in der Regel Laden nur die Zeilen, die Sie in einen Cache anzuzeigen und zu behandeln müssen <xref:System.Windows.Forms.DataGridView> Ereignisse interagieren und den Cache zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="398a0-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="398a0-109">Weitere Informationen finden Sie unter [Implementieren des virtuellen Modus mit Just-in-Time-Laden von Daten im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="398a0-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="398a0-110">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="398a0-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="398a0-111">Erstellen des Formulars</span><span class="sxs-lookup"><span data-stu-id="398a0-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="398a0-112">Implementieren des virtuellen Modus</span><span class="sxs-lookup"><span data-stu-id="398a0-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="398a0-113">Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="398a0-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="398a0-114">Der folgende Code enthält einige grundlegende Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="398a0-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="398a0-115">Diese einige Variablen deklariert, die in späteren Schritten verwendet werden, und bietet eine `Main` -Methode, und bietet ein einfaches Formularlayout im Konstruktor Klasse.</span><span class="sxs-lookup"><span data-stu-id="398a0-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="398a0-116">Implementieren Sie einen Handler für Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> steuern und der Datenspeicher mit Beispieldaten gefüllt.</span><span class="sxs-lookup"><span data-stu-id="398a0-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="398a0-117">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValueNeeded> -Ereignis, das den angeforderten Zelle-Wert aus dem Datenspeicher abruft oder `Customer` Objekt derzeit in Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="398a0-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="398a0-118">Dieses Ereignis tritt auf, wenn die <xref:System.Windows.Forms.DataGridView> Steuerelement eine Zelle gezeichnet werden muss.</span><span class="sxs-lookup"><span data-stu-id="398a0-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="398a0-119">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValuePushed> -Ereignis, das einen bearbeitete Zellenwert in speichert die `Customer` Objekt, das die bearbeitete Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="398a0-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="398a0-120">Dieses Ereignis tritt auf, wenn der Benutzer die Änderung eines Zelle ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="398a0-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="398a0-121">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.NewRowNeeded> -Ereignis, ein neues erstellt `Customer` Objekt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="398a0-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="398a0-122">Dieses Ereignis tritt auf, wenn der Benutzer die Zeile für neue Datensätze eingibt.</span><span class="sxs-lookup"><span data-stu-id="398a0-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="398a0-123">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.RowValidated> Ereignis, neue oder geänderte Zeilen im Datenspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="398a0-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="398a0-124">Dieses Ereignis tritt auf, wenn der Benutzer die aktuelle Zeile ändert.</span><span class="sxs-lookup"><span data-stu-id="398a0-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="398a0-125">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> Ereignis, das angibt, ob die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus befindet oder einmal außerhalb des Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="398a0-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="398a0-126">In der Standardeinstellung <xref:System.Windows.Forms.DataGridView.CancelRowEdit> tritt auf, beim Zurücksetzen von Zeilen, wenn keine Zellen in der aktuellen Zeile geändert wurden, wenn die <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> -Eigenschaftensatz auf `true` in die <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="398a0-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="398a0-127">Dieses Ereignis ist nützlich, wenn der Commit-Bereich zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="398a0-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="398a0-128">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CancelRowEdit> -Ereignis, das die Werte der verwirft die `Customer` Objekt, das die aktuelle Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="398a0-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="398a0-129">Dieses Ereignis tritt auf, wenn der Benutzer das Zurücksetzen einer Zeile durch Drücken der ESC-Taste zweimal im Bearbeitungsmodus befindet oder einmal außerhalb des Bearbeitungsmodus signalisiert.</span><span class="sxs-lookup"><span data-stu-id="398a0-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="398a0-130">Dieses Ereignis tritt nicht auf, wenn keine Zellen in der aktuellen Zeile geändert wurden oder wenn der Wert des der <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> eingestellt wurde `false` in einer <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="398a0-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="398a0-131">Implementieren Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.UserDeletingRow> -Ereignis, das Löscht eine vorhandene `Customer` Objekt aus dem Datenspeicher, zusammen oder verwirft eine ungespeicherte `Customer` Objekt, das eine neu erstellte Zeile darstellt.</span><span class="sxs-lookup"><span data-stu-id="398a0-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="398a0-132">Dieses Ereignis tritt auf, wenn der Benutzer eine Zeile löscht, indem Sie auf einen Zeilenheader und die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="398a0-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="398a0-133">Implementieren Sie eine einfache `Customers` Klasse darstellen, die die Datenelemente, die von diesem Codebeispiel wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="398a0-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="398a0-134">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="398a0-134">Testing the Application</span></span>  
 <span data-ttu-id="398a0-135">Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.</span><span class="sxs-lookup"><span data-stu-id="398a0-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="398a0-136">So testen Sie das Formular</span><span class="sxs-lookup"><span data-stu-id="398a0-136">To test the form</span></span>  
  
- <span data-ttu-id="398a0-137">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="398a0-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="398a0-138">Sie sehen eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit drei Kundendatensätze aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="398a0-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="398a0-139">Sie können ändern Sie die Werte aus mehreren Zellen in einer Zeile, und drücken Sie ESC, zweimal im Bearbeitungsmodus befindet und einmal außerhalb Bearbeitungszustand versetzt, damit die gesamte Zeile auf die ursprünglichen Werte zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="398a0-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="398a0-140">Wenn Sie ändern, hinzufügen oder Löschen von Zeilen im Steuerelement `Customer` Objekte im Datenspeicher geändert, hinzugefügt oder ebenfalls gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="398a0-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="398a0-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="398a0-141">Next Steps</span></span>  
 <span data-ttu-id="398a0-142">Diese Anwendung verfügt über einen grundlegenden Überblick über die Ereignisse müssen Sie zum Implementieren virtuellen Modus im behandeln die <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="398a0-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="398a0-143">Sie können diese einfache vorlagenanwendung auf vielfältige Weise verbessern:</span><span class="sxs-lookup"><span data-stu-id="398a0-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="398a0-144">Implementieren Sie einen Datenspeicher, der Werte aus einer externen Datenbank speichert.</span><span class="sxs-lookup"><span data-stu-id="398a0-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="398a0-145">Der Cache sollte abrufen und die Werte nach Bedarf zu verwerfen, sodass sie nur enthält, was für die Anzeige während der Verarbeitung von einem kleinen Teil des Arbeitsspeichers auf dem Clientcomputer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="398a0-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="398a0-146">Optimieren Sie die Leistung des Datenspeichers je nach Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="398a0-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="398a0-147">Beispielsweise empfiehlt es sich um für langsame Netzwerkverbindungen anstelle von Client-Computer-Memory-Einschränkungen zu kompensieren, indem Sie einen größeren Cache und Verringerung der Anzahl von Abfragen.</span><span class="sxs-lookup"><span data-stu-id="398a0-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="398a0-148">Weitere Informationen zum Zwischenspeichern von Werten aus einer externen Datenbank finden Sie unter [Vorgehensweise: Implementieren des virtuellen Modus mit Just-in-Time-Daten laden in das Windows Forms-DataGridView-Steuerelement](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="398a0-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398a0-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="398a0-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="398a0-150">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="398a0-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="398a0-151">Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="398a0-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="398a0-152">Implementieren des virtuellen Modus mit Just-In-Time-Laden von Daten in das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="398a0-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="398a0-153">Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="398a0-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
