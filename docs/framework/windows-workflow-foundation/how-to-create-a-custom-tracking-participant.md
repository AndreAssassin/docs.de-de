---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Nachverfolgungskomponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: 64320a8f4799e79f54348e5381ed2d8ed49d496b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338175"
---
# <a name="how-to-create-a-custom-tracking-participant"></a><span data-ttu-id="0bca1-102">Vorgehensweise: Erstellen einer benutzerdefinierten Nachverfolgungskomponente</span><span class="sxs-lookup"><span data-stu-id="0bca1-102">How to: Create a Custom Tracking Participant</span></span>
<span data-ttu-id="0bca1-103">Die Workflownachverfolgung gewährt Einblick in den Status der Workflowausführung.</span><span class="sxs-lookup"><span data-stu-id="0bca1-103">Workflow tracking provides visibility into the status of workflow execution.</span></span> <span data-ttu-id="0bca1-104">Die Workflowlaufzeit gibt Überwachungsdatensätze aus, die Ereignisse im Workflow- und Aktivitätslebenszyklus, Lesezeichenwiederaufnahmen und Fehler beschreiben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-104">The workflow runtime emits tracking records that describe workflow lifecycle events, activity lifecycle events, bookmark resumptions, and faults.</span></span> <span data-ttu-id="0bca1-105">Diese Überwachungsdatensätze werden von den Überwachungsteilnehmern genutzt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-105">These tracking records are consumed by tracking participants.</span></span> <span data-ttu-id="0bca1-106">Windows Workflow Foundation (WF) enthält einen standardmäßigen Überwachungsteilnehmer, der Nachverfolgungsdatensätze als Ereignisse der Ereignisablaufverfolgung für Windows (ETW) schreibt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-106">Windows Workflow Foundation (WF) includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="0bca1-107">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-107">If that does not meet your requirements, you can also write a custom tracking participant.</span></span> <span data-ttu-id="0bca1-108">In diesem Schritt des Lernprogramms wird beschrieben, wie ein benutzerdefinierter Überwachungsteilnehmer und ein Nachverfolgungsprofil erstellt werden, die die Ausgabe von `WriteLine`-Aktivitäten aufzeichnen, damit sie dem Benutzer angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="0bca1-108">This tutorial step describes how to create a custom tracking participant and tracking profile that capture the output of `WriteLine` activities so that they can be displayed to the user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bca1-109">Ein Thema im Lernprogramm "Erste Schritte" hängt jeweils von den vorherigen Themen ab.</span><span class="sxs-lookup"><span data-stu-id="0bca1-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="0bca1-110">Um dieses Thema abzuschließen, müssen Sie die vorherigen Themen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-110">To complete this topic, you must first complete the previous topics.</span></span> <span data-ttu-id="0bca1-111">Um den download einer vervollständigten Version oder eine Videodemonstration des Lernprogramms anzuzeigen, finden Sie unter [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="0bca1-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="to-create-the-custom-tracking-participant"></a><span data-ttu-id="0bca1-112">So erstellen Sie den benutzerdefinierten Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0bca1-112">To create the custom tracking participant</span></span>  
  
1. <span data-ttu-id="0bca1-113">Mit der rechten Maustaste **NumberGuessWorkflowHost** in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="0bca1-113">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="0bca1-114">Typ `StatusTrackingParticipant` in die **Namen** ein, und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0bca1-114">Type `StatusTrackingParticipant` into the **Name** box, and click **Add**.</span></span>  
  
2. <span data-ttu-id="0bca1-115">Fügen Sie die folgenden `using`-Anweisungen (oder `Imports`-Anweisungen) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bca1-115">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3. <span data-ttu-id="0bca1-116">Ändern Sie `StatusTrackingParticipant`-Klasse so, dass sie von `TrackingParticipant` erbt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-116">Modify the `StatusTrackingParticipant` class so that it inherits from `TrackingParticipant`.</span></span>  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4. <span data-ttu-id="0bca1-117">Fügen Sie die folgende `Track`-Methodenüberschreibung hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bca1-117">Add the following `Track` method override.</span></span> <span data-ttu-id="0bca1-118">Es gibt mehrere Typen von Überwachungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="0bca1-118">There are several different types of tracking records.</span></span> <span data-ttu-id="0bca1-119">Nur die Ausgabe der `WriteLine`-Aktivitäten, die in den Überwachungsdatensätzen für Aktivitäten enthalten sind, ist für uns interessant.</span><span class="sxs-lookup"><span data-stu-id="0bca1-119">We are interested in the output of `WriteLine` activities, which are contained in activity tracking records.</span></span> <span data-ttu-id="0bca1-120">Wenn `TrackingRecord` ein `ActivityTrackingRecord` für eine `WriteLine`-Aktivität ist, wird der `Text` von `WriteLine` an eine Datei angefügt, die nach der `InstanceId` des Workflows benannt ist.</span><span class="sxs-lookup"><span data-stu-id="0bca1-120">If the `TrackingRecord` is an `ActivityTrackingRecord` for a `WriteLine` activity, the `Text` of the `WriteLine` is appended to a file named after the `InstanceId` of the workflow.</span></span> <span data-ttu-id="0bca1-121">In diesem Lernprogramm wird die Datei im aktuellen Ordner der Hostanwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0bca1-121">In this tutorial, the file is saved to the current folder of the host application.</span></span>  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="0bca1-122">Wenn kein Nachverfolgungsprofil angegeben ist, wird das standardmäßige Nachverfolgungsprofil verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bca1-122">When no tracking profile is specified, the default tracking profile is used.</span></span> <span data-ttu-id="0bca1-123">Wenn das standardmäßige Nachverfolgungsprofil verwendet wird, werden Überwachungsdatensätze für alle `ActivityStates` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-123">When the default tracking profile is used, tracking records are emitted for all `ActivityStates`.</span></span> <span data-ttu-id="0bca1-124">Da Text während des Lebenszyklus der `WriteLine`-Aktivität nur einmal aufgezeichnet werden muss, extrahieren wir nur den Text des `ActivityStates.Executing`-Zustands.</span><span class="sxs-lookup"><span data-stu-id="0bca1-124">Because we only need to capture the text one time during the lifecycle of the `WriteLine` activity, we only extract the text from the `ActivityStates.Executing` state.</span></span> <span data-ttu-id="0bca1-125">In [erstellen das nachverfolgungsprofil und registrieren den Überwachungsteilnehmer](#to-create-the-tracking-profile-and-register-the-tracking-participant), ein Überwachungsprofil erstellt, der angibt, dass nur `WriteLine` `ActivityStates.Executing` Nachverfolgungsdatensätze werden ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-125">In [To create the tracking profile and register the tracking participant](#to-create-the-tracking-profile-and-register-the-tracking-participant), a tracking profile is created that specifies that only `WriteLine` `ActivityStates.Executing` tracking records are emitted.</span></span>  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a><span data-ttu-id="0bca1-126">So erstellen Sie das Nachverfolgungsprofil und registrieren den Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="0bca1-126">To create the tracking profile and register the tracking participant</span></span>  
  
1. <span data-ttu-id="0bca1-127">Mit der rechten Maustaste **WorkflowHostForm** in **Projektmappen-Explorer** , und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="0bca1-127">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="0bca1-128">Fügen Sie die folgende `using`-Anweisung (oder `Imports`-Anweisung) mit den anderen `using`-Anweisungen (oder `Imports`-Anweisungen) am Anfang der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bca1-128">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3. <span data-ttu-id="0bca1-129">Fügen Sie `ConfigureWorkflowApplication` den folgenden Code unmittelbar nach dem Code, durch den `StringWriter` den Workflowerweiterungen hinzugefügt wird, und vor den Handlern des Workflowlebenszyklus hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bca1-129">Add the following code to `ConfigureWorkflowApplication` just after the code that adds the `StringWriter` to the workflow extensions and before the workflow lifecycle handlers.</span></span>  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     <span data-ttu-id="0bca1-130">Dieses Nachverfolgungsprofil gibt an, dass nur Zustandsdatensätze für `WriteLine`-Aktivitäten im `Executing`-Zustand an den benutzerdefinierten Überwachungsteilnehmer ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0bca1-130">This tracking profile specifies that only activity state records for `WriteLine` activities in the `Executing` state are emitted to the custom tracking participant.</span></span>  
  
     <span data-ttu-id="0bca1-131">Nachdem der Code hinzugefügt wurde, sieht der Anfang von `ConfigureWorkflowApplication` wie im folgenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="0bca1-131">After adding the code, the start of `ConfigureWorkflowApplication` will look like the following example.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
## <a name="to-display-the-tracking-information"></a><span data-ttu-id="0bca1-132">So zeigen Sie die Nachverfolgungsinformationen an</span><span class="sxs-lookup"><span data-stu-id="0bca1-132">To display the tracking information</span></span>  
  
1. <span data-ttu-id="0bca1-133">Mit der rechten Maustaste **WorkflowHostForm** in **Projektmappen-Explorer** , und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="0bca1-133">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="0bca1-134">Fügen Sie im `InstanceId_SelectedIndexChanged`-Handler den folgenden Code unmittelbar nach dem Code hinzu, durch den das Statusfenster gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="0bca1-134">In the `InstanceId_SelectedIndexChanged` handler, add the following code immediately after the code that clears the status window.</span></span>  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     <span data-ttu-id="0bca1-135">Wenn ein neuer Workflow in der Workflowliste ausgewählt wird, werden die Überwachungsdatensätze für diesen Workflow geladen und im Statusfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-135">When a new workflow is selected in the workflow list, the tracking records for that workflow are loaded and displayed in the status window.</span></span> <span data-ttu-id="0bca1-136">Im folgenden Beispiel ist der abgeschlossene `InstanceId_SelectedIndexChanged`-Handler dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-136">The following example is the completed `InstanceId_SelectedIndexChanged` handler.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
## <a name="to-build-and-run-the-application"></a><span data-ttu-id="0bca1-137">So erstellen und führen Sie die Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="0bca1-137">To build and run the application</span></span>  
  
1. <span data-ttu-id="0bca1-138">Drücken Sie STRG+UMSCHALT+B, um die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0bca1-138">Press Ctrl+Shift+B to build the application.</span></span>  
  
2. <span data-ttu-id="0bca1-139">Drücken Sie STRG+F5, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0bca1-139">Press Ctrl+F5 to start the application.</span></span>  
  
3. <span data-ttu-id="0bca1-140">Wählen Sie einen Bereich für das Ratespiel und der Typ des Workflows zu starten, und klicken Sie auf **New Game**.</span><span class="sxs-lookup"><span data-stu-id="0bca1-140">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="0bca1-141">Geben Sie eine Schätzung in die **Schätzung** ein, und klicken Sie auf **wechseln** Ihre Schätzung zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0bca1-141">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="0bca1-142">Beachten Sie, dass der Status des Workflows im Statusfenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0bca1-142">Note that the status of the workflow is displayed in the status window.</span></span> <span data-ttu-id="0bca1-143">Diese Ausgabe wird von den `WriteLine`-Aktivitäten aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0bca1-143">This output is captured from the `WriteLine` activities.</span></span> <span data-ttu-id="0bca1-144">Wechseln Sie zu einem anderen Workflow, indem Sie einen Konverter auswählen der **Workflowinstanz-Id** Kombinationsfeld und beachten Sie, dass der Status des aktuellen Workflows entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="0bca1-144">Switch to a different workflow by selecting one from the **Workflow Instance Id** combo box and note that the status of the current workflow is removed.</span></span> <span data-ttu-id="0bca1-145">Wechseln Sie zurück zum vorherigen Workflow. Wie im folgenden Beispiel dargestellt, wird der Status wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-145">Switch back to the previous workflow and note that the status is restored, similar to the following example.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0bca1-146">Wenn Sie zu einem Workflow wechseln, der vor dem Aktivieren der Nachverfolgung gestartet wurde, wird kein Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-146">If you switch to a workflow that was started before tracking was enabled no status is displayed.</span></span> <span data-ttu-id="0bca1-147">Wenn Sie zusätzliche Schätzwerte eingeben, wird deren Status jedoch gespeichert, da die Nachverfolgung jetzt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0bca1-147">However if you make additional guesses, their status is saved because tracking is now enabled.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```
    
    > [!NOTE]
    > <span data-ttu-id="0bca1-148">Diese Informationen sind hilfreich, um den Bereich der Zufallszahl bestimmen. Sie sagen jedoch nichts darüber aus, welche Schätzwerte zuvor angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="0bca1-148">This information is useful for determining the range of the random number, but it does not contain any information about what guesses have been previously made.</span></span> <span data-ttu-id="0bca1-149">Diese Informationen sind im nächsten Schritt [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="0bca1-149">This information is in the next step, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    <span data-ttu-id="0bca1-150">Notieren Sie sich die Workflowinstanz-ID, und durchlaufen Sie das Spiel bis zum Ende.</span><span class="sxs-lookup"><span data-stu-id="0bca1-150">Make a note of the workflow instance id, and play the game through to its completion.</span></span>
  
4. <span data-ttu-id="0bca1-151">Öffnen Sie Windows Explorer, und navigieren Sie zu der **NumberGuessWorkflowHost\bin\debug** Ordner (oder **"bin\Release"** je nach den projekteinstellungen).</span><span class="sxs-lookup"><span data-stu-id="0bca1-151">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="0bca1-152">Zusätzlich zu den ausführbaren Projektdateien sehen Sie jetzt auch Dateien mit GUID-Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="0bca1-152">Note that in addition to the project executable files there are files with guid filenames.</span></span> <span data-ttu-id="0bca1-153">Identifizieren Sie die Datei, die der Workflowinstanz-ID des im vorherigen Schritt abgeschlossenen Workflows entspricht, und öffnen Sie sie im Editor.</span><span class="sxs-lookup"><span data-stu-id="0bca1-153">Identify the one that corresponds to the workflow instance id from the completed workflow in the previous step and open it in Notepad.</span></span> <span data-ttu-id="0bca1-154">Die Nachverfolgungsinformationen enthalten in etwa die folgenden Angaben.</span><span class="sxs-lookup"><span data-stu-id="0bca1-154">The tracking information contains information similar to the following.</span></span>  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    <span data-ttu-id="0bca1-155">Abgesehen davon, dass Schätzwerte des Benutzers fehlen, enthalten diese Nachverfolgungsinformationen auch keine Angaben über den endgültigen Schätzwert des Workflows.</span><span class="sxs-lookup"><span data-stu-id="0bca1-155">In addition to the absence of the user's guesses, this tracking data does not contain information about the final guess of the workflow.</span></span> <span data-ttu-id="0bca1-156">Das liegt daran, dass die Nachverfolgungsinformationen nur die `WriteLine`-Ausgabe des Workflows enthalten und die abschließend angezeigte Meldung nach Abschluss des Workflows vom `Completed`-Handler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bca1-156">That is because the tracking information consists only of the `WriteLine` output from the workflow, and the final message that is displayed is done so from the `Completed` handler after the workflow completes.</span></span> <span data-ttu-id="0bca1-157">Im nächsten Schritt des Tutorials [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), die vorhandene `WriteLine` Aktivitäten werden geändert, um die Anzeige Schätzwerte des Benutzers und eine zusätzliche `WriteLine` Aktivität hinzugefügt wird, die die Endergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0bca1-157">In next step of the tutorial, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), the existing `WriteLine` activities are modified to display the user's guesses, and an additional `WriteLine` activity is added that displays the final results.</span></span> <span data-ttu-id="0bca1-158">Nachdem diese Änderungen integriert sind, [Vorgehensweise: Hosten mehrerer Workflowversionen zu einem Workflow Seite-an-Seite](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) wird veranschaulicht, wie mehrere Versionen eines Workflows gleichzeitig gehostet.</span><span class="sxs-lookup"><span data-stu-id="0bca1-158">After these changes are integrated, [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) demonstrates how to host multiple versions of a workflow at the same time.</span></span>
