---
title: Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 549acec8b8101312d48bd20e63a4a988b798ff38
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669445"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="a414e-102">Erstellen von Workflowaktivitäten mit der CodeActivity-Klasse</span><span class="sxs-lookup"><span data-stu-id="a414e-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>
<span data-ttu-id="a414e-103">Aktivitäten, die durch das Erben von <xref:System.Activities.CodeActivity> erstellt werden, können das grundlegende imperative Verhalten implementieren, indem sie die <xref:System.Activities.CodeActivity.Execute%2A>-Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a414e-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="a414e-104">Verwenden von CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="a414e-104">Using CodeActivityContext</span></span>
 <span data-ttu-id="a414e-105">Innerhalb der <xref:System.Activities.CodeActivity.Execute%2A>-Methode kann mithilfe von Membern des `context`-Parameters vom Typ <xref:System.Activities.CodeActivityContext> auf Funktionen des Workflows zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a414e-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="a414e-106">Über <xref:System.Activities.CodeActivityContext> sind unter anderem folgende Funktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a414e-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

- <span data-ttu-id="a414e-107">Abrufen und Festlegen der Werte von Variablen und Argumenten</span><span class="sxs-lookup"><span data-stu-id="a414e-107">Getting and setting the values of variables and arguments.</span></span>

- <span data-ttu-id="a414e-108">Benutzerdefinierte Überwachungsfunktionen mit <xref:System.Activities.CodeActivityContext.Track%2A></span><span class="sxs-lookup"><span data-stu-id="a414e-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="a414e-109">Zugreifen auf die Ausführungseigenschaften der Aktivität mithilfe von <xref:System.Activities.CodeActivityContext.GetProperty%2A></span><span class="sxs-lookup"><span data-stu-id="a414e-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="a414e-110">So erstellen Sie eine benutzerdefinierte Aktivität, die von CodeActivity erbt</span><span class="sxs-lookup"><span data-stu-id="a414e-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="a414e-111">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a414e-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="a414e-112">Wählen Sie **Datei**, **neue**, und klicken Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a414e-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="a414e-113">Wählen Sie **Workflow 4.0** unter **Visual C#-** in die **Projekttypen** , und wählen die **v2010** Knoten.</span><span class="sxs-lookup"><span data-stu-id="a414e-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="a414e-114">Wählen Sie **Aktivitätsbibliothek** in die **Vorlagen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="a414e-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="a414e-115">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="a414e-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="a414e-116">Mit der rechten Maustaste Activity1.xaml im HelloActivity-Projekt, und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="a414e-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="a414e-117">Maustaste auf das HelloActivity-Projekt, und wählen Sie **hinzufügen** , und klicken Sie dann **Klasse**.</span><span class="sxs-lookup"><span data-stu-id="a414e-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="a414e-118">Nennen Sie die neue Klasse HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="a414e-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="a414e-119">Fügen Sie der Datei "HelloActivity.cs" die folgenden `using`-Direktiven hinzu.</span><span class="sxs-lookup"><span data-stu-id="a414e-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="a414e-120">Legen Sie fest, dass die neue Klasse von <xref:System.Activities.CodeActivity> erben soll, indem Sie der Klassendeklaration eine Basisklasse hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a414e-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="a414e-121">Fügen Sie der Klasse die Funktionalität hinzu, indem Sie eine <xref:System.Activities.CodeActivity.Execute%2A>-Methode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a414e-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="a414e-122">Verwenden Sie die <xref:System.Activities.CodeActivityContext>-Instanz, um einen Nachverfolgungsdatensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a414e-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
