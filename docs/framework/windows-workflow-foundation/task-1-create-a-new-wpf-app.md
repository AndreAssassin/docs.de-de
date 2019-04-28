---
title: 'Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 63b84e4fd2c88d98fbf417ee1f55ec203d295116
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641641"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="f02ab-102">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="f02ab-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="f02ab-103">In dieser Aufgabe, Sie erstellen eine leere Windows Presentation Foundation (WPF)-Anwendung mithilfe der WPF-Anwendungsvorlage von Visual Studio-Vorlage und fügen Sie Verweise auf die entsprechenden [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflowassemblys.</span><span class="sxs-lookup"><span data-stu-id="f02ab-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="f02ab-104">So erstellen Sie das WPF-Anwendungsprojekt</span><span class="sxs-lookup"><span data-stu-id="f02ab-104">To create the WPF Application project</span></span>  
  
1. <span data-ttu-id="f02ab-105">Öffnen Sie Visual Studio und klicken Sie auf die **Datei** Startmenü **neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="f02ab-106">In der **neues Projekt** Dialogfeld wählen **Visual C#**  oder **Visual Basic** aus der **installierte Vorlagen** im linken Bereich die Seite des Felds.</span><span class="sxs-lookup"><span data-stu-id="f02ab-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="f02ab-107">Wenn die Sprache Ihrer Wahl nicht angezeigt wird, suchen Sie unter **andere Sprachen**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3. <span data-ttu-id="f02ab-108">Wählen Sie **Windows** in die **installierte Vorlagen** Bereich.</span><span class="sxs-lookup"><span data-stu-id="f02ab-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4. <span data-ttu-id="f02ab-109">Im oberen Bereich sicher, dass (Standardwert) **.NET Framework 4** wurde, und wählen Sie dann im Dropdown-Listenfeld ausgewählte **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5. <span data-ttu-id="f02ab-110">Legen Sie den Namen des Projekts, das **HostingApplication** am unteren Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="f02ab-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6. <span data-ttu-id="f02ab-111">Legen Sie den Namen der Projektmappe auf **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7. <span data-ttu-id="f02ab-112">Klicken Sie auf **OK** das Anwendungsprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f02ab-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="f02ab-113">Visual Studio eine einfache WPF-UI für Ihre Anwendung erstellt und enthält die entsprechende XAML und Code-Behind-Dateien.</span><span class="sxs-lookup"><span data-stu-id="f02ab-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8. <span data-ttu-id="f02ab-114">Fügen Sie Verweise auf **WorkflowModel** Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f02ab-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="f02ab-115">Klicken Sie hierzu in **Projektmappen-Explorer**, mit der rechten Maustaste die **HostingApplication** Projekt, und wählen **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="f02ab-116">In der **Verweis hinzufügen** Dialogfeld klicken Sie auf die **.NET** , halten Sie die STRG-Taste gedrückt, wählen Sie die folgenden Assemblys, und klicken Sie dann auf **OK**:</span><span class="sxs-lookup"><span data-stu-id="f02ab-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    - <span data-ttu-id="f02ab-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="f02ab-117">System.Activities</span></span>  
  
    - <span data-ttu-id="f02ab-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="f02ab-118">System.Activities.Presentation</span></span>  
  
    - <span data-ttu-id="f02ab-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="f02ab-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="f02ab-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f02ab-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="f02ab-121">Finden Sie unter [Aufgabe 2: Hosten des Workflow-Designers](task-2-host-the-workflow-designer.md) erfahren, wie die Workflow-Designer-Entwurfs-Canvas zu hosten.</span><span class="sxs-lookup"><span data-stu-id="f02ab-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02ab-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f02ab-122">See also</span></span>

- [<span data-ttu-id="f02ab-123">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="f02ab-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="f02ab-124">Task 2: Hosten des Workflowdesigners</span><span class="sxs-lookup"><span data-stu-id="f02ab-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
