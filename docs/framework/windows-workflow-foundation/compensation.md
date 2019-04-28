---
title: Kompensierung
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: af29ba61ff5bede9208f2ab706f5e0ce1ff12274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774282"
---
# <a name="compensation"></a><span data-ttu-id="b0386-102">Kompensierung</span><span class="sxs-lookup"><span data-stu-id="b0386-102">Compensation</span></span>
<span data-ttu-id="b0386-103">Kompensierung in Windows Workflow Foundation (WF) ist der Mechanismus, mit dem zuvor Abgeschlossene Arbeitsaufgaben rückgängig gemacht bzw. kompensiert (gemäß der von der Anwendung definierten Logik) werden kann, wenn nachfolgend ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0386-103">Compensation in Windows Workflow Foundation (WF) is the mechanism by which previously completed work can be undone or compensated (following the logic defined by the application) when a subsequent failure occurs.</span></span> <span data-ttu-id="b0386-104">In diesem Abschnitt wird beschrieben, wie die Kompensation in Workflows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0386-104">This section describes how to use compensation in workflows.</span></span>  
  
## <a name="compensation-vs-transactions"></a><span data-ttu-id="b0386-105">Kompensation und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="b0386-105">Compensation vs. Transactions</span></span>  
 <span data-ttu-id="b0386-106">Eine Transaktion ermöglicht es Ihnen, mehrere Vorgänge in nur einer Arbeitseinheit zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="b0386-106">A transaction allows you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="b0386-107">Wenn Sie Transaktionen verwenden, kann Ihre Anwendung alle Änderungen zurücknehmen (Rollback), die innerhalb der Transaktion ausgeführt wurden, falls während des Transaktionsprozesses ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0386-107">Using a transaction gives your application the ability to abort (roll back) all changes executed from within the transaction if any errors occur during any part of the transaction process.</span></span> <span data-ttu-id="b0386-108">Die Verwendung von Transaktionen eignet sich jedoch möglicherweise nicht für Arbeitsaufgaben mit langer Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b0386-108">However, using transactions may not be appropriate if the work is long running.</span></span> <span data-ttu-id="b0386-109">Angenommen, eine Anwendung zum Planen von Reisen wird als Workflow implementiert.</span><span class="sxs-lookup"><span data-stu-id="b0386-109">For example, a travel planning application is implemented as a workflow.</span></span> <span data-ttu-id="b0386-110">Die Schritte des Workflows bestehen z. B. aus der Buchung eines Flugs, dem Warten auf die Genehmigung des Managers und der anschließenden Bezahlung des Flugs.</span><span class="sxs-lookup"><span data-stu-id="b0386-110">The steps of the workflow may consist of booking a flight, waiting for manager approval, and then paying for the flight.</span></span> <span data-ttu-id="b0386-111">Da sich dieser Prozess über mehrere Tage hinziehen kann, ist es nicht sinnvoll, die Buchungs- und Zahlungsschritte in derselben Transaktion zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b0386-111">This process could take many days and it is not practical for the steps of booking and paying for the flight to participate in the same transaction.</span></span> <span data-ttu-id="b0386-112">In einem Szenario wie diesem kann der Buchungsschritt des Workflows mittels Kompensation rückgängig gemacht werden, wenn an späterer Stelle ein Verarbeitungsfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0386-112">In a scenario such as this, compensation could be used to undo the booking step of the workflow if there is a failure later in the processing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0386-113">Dieses Thema behandelt die Kompensation in Workflows.</span><span class="sxs-lookup"><span data-stu-id="b0386-113">This topic covers compensation in workflows.</span></span> <span data-ttu-id="b0386-114">Weitere Informationen zu Transaktionen in Workflows finden Sie unter [Transaktionen](workflow-transactions.md) und <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="b0386-114">For more information about transactions in workflows, see [Transactions](workflow-transactions.md) and <xref:System.Activities.Statements.TransactionScope>.</span></span> <span data-ttu-id="b0386-115">Weitere Informationen über Transaktionen finden Sie unter <xref:System.Transactions?displayProperty=nameWithType> und <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0386-115">For more information about transactions, see <xref:System.Transactions?displayProperty=nameWithType> and <xref:System.Transactions.Transaction?displayProperty=nameWithType>.</span></span>  
  
## <a name="using-compensableactivity"></a><span data-ttu-id="b0386-116">Verwenden von CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="b0386-116">Using CompensableActivity</span></span>  
 <span data-ttu-id="b0386-117">Das <xref:System.Activities.Statements.CompensableActivity>-Objekt ist die wichtigste Kompensationsaktivität in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0386-117"><xref:System.Activities.Statements.CompensableActivity> is the core compensation activity in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="b0386-118">Alle Aktivitäten zum Ausführen einer Arbeit, die möglicherweise kompensiert werden soll, werden in das <xref:System.Activities.Statements.CompensableActivity.Body%2A>-Element eines <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b0386-118">Any activities that perform work that may need to be compensated are placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="b0386-119">In diesem Beispiel wird der Reservierungsschritt der Buchung eines Flugs in das <xref:System.Activities.Statements.CompensableActivity.Body%2A>-Element eines <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt, und der Abbruch der Reservierung wird in das <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Element eingefügt.</span><span class="sxs-lookup"><span data-stu-id="b0386-119">In this example, the reservation step of purchasing a flight is placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> and the cancellation of the reservation is placed into the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>.</span></span> <span data-ttu-id="b0386-120">Im Workflow folgen unmittelbar auf das <xref:System.Activities.Statements.CompensableActivity>-Objekt zwei Aktivitäten, für die eine Genehmigung durch einen Manager erfolgen muss und die dann die Buchung des Flugs abschließen.</span><span class="sxs-lookup"><span data-stu-id="b0386-120">Immediately following the <xref:System.Activities.Statements.CompensableActivity> in the workflow are two activities that wait for manager approval and then complete the purchasing step of the flight.</span></span> <span data-ttu-id="b0386-121">Wenn der Workflow aufgrund eines Fehlers abgebrochen wird, nachdem das <xref:System.Activities.Statements.CompensableActivity>-Objekt erfolgreich abgeschlossen wurde, werden die Aktivitäten im <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Handler geplant und der Flug wird gestrichen.</span><span class="sxs-lookup"><span data-stu-id="b0386-121">If an error condition causes the workflow to be canceled after the <xref:System.Activities.Statements.CompensableActivity> has successfully completed, then the activities in the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> handler are scheduled and the flight is canceled.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 <span data-ttu-id="b0386-122">Das folgende Beispiel ist der Workflow in XAML.</span><span class="sxs-lookup"><span data-stu-id="b0386-122">The following example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="b0386-123">Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-123">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="b0386-124">**ReserveFlight: Ticket wird reserviert.**</span><span class="sxs-lookup"><span data-stu-id="b0386-124">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="b0386-125">**ManagerApproval: Manager-Genehmigung erhalten.** </span><span class="sxs-lookup"><span data-stu-id="b0386-125">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="b0386-126">**PurchaseFlight: Ticket wird gekauft.** </span><span class="sxs-lookup"><span data-stu-id="b0386-126">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="b0386-127">**Workflow wurde erfolgreich abgeschlossen, mit dem Status: Geschlossen.**</span><span class="sxs-lookup"><span data-stu-id="b0386-127">**Workflow completed successfully with status: Closed.**</span></span>    
> [!NOTE]
>  <span data-ttu-id="b0386-128">Die Beispielaktivitäten in diesem Thema z. B. `ReserveFlight` geben ihren Namen und Zweck auf der Konsole an, um die Reihenfolge zu veranschaulichen, in der die Aktivitäten ausgeführt werden, wenn eine Kompensation auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0386-128">The sample activities in this topic such as `ReserveFlight` display their name and purpose to the console to help illustrate the order in which the activities are executed when compensation occurs.</span></span>  
  
### <a name="default-workflow-compensation"></a><span data-ttu-id="b0386-129">Standard-Workflowkompensation</span><span class="sxs-lookup"><span data-stu-id="b0386-129">Default Workflow Compensation</span></span>  
 <span data-ttu-id="b0386-130">Standardmäßig wird nach dem Abbruch eines Workflows die Kompensationslogik für jede kompensierbare Aktivität ausgeführt, die erfolgreich abgeschlossen wurde und noch nicht bestätigt oder kompensiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b0386-130">By default, if the workflow is canceled, the compensation logic is run for any compensable activity that has successfully completely and has not already been confirmed or compensated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0386-131">Wenn eine <xref:System.Activities.Statements.CompensableActivity> ist *bestätigt*, Kompensierung für die Aktivität nicht mehr aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0386-131">When a <xref:System.Activities.Statements.CompensableActivity> is *confirmed*, compensation for the activity can no longer be invoked.</span></span> <span data-ttu-id="b0386-132">Der Bestätigungsvorgang wird weiter unten in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0386-132">The confirmation process is described later in this section.</span></span>  
  
 <span data-ttu-id="b0386-133">In diesem Beispiel wird eine Ausnahme ausgelöst, nachdem der Flug reserviert wurde und bevor der Genehmigungsschritt durch den Manager erfolgen konnte.</span><span class="sxs-lookup"><span data-stu-id="b0386-133">In this example, an exception is thrown after the flight is reserved but before the manager approval step.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 <span data-ttu-id="b0386-134">Dieses Beispiel ist der Workflow in XAML.</span><span class="sxs-lookup"><span data-stu-id="b0386-134">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 <span data-ttu-id="b0386-135">Wenn der Workflow aufgerufen wird, wird die simulierte Fehlerbedingungsausnahme von der Hostanwendung in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> behandelt, der Workflow wird abgebrochen, und die Kompensationslogik wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0386-135">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the compensation logic is invoked.</span></span>  
  
 <span data-ttu-id="b0386-136">**ReserveFlight: Ticket wird reserviert.**</span><span class="sxs-lookup"><span data-stu-id="b0386-136">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="b0386-137">**SimulatedErrorCondition: Auslösen von ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="b0386-137">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="b0386-138">**Nicht behandelte Workflowausnahme:** </span><span class="sxs-lookup"><span data-stu-id="b0386-138">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="b0386-139">**System.ApplicationException: Simulierte fehlerbedingung im Workflow.** </span><span class="sxs-lookup"><span data-stu-id="b0386-139">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="b0386-140">**CancelFlight: Ticket wird storniert.** </span><span class="sxs-lookup"><span data-stu-id="b0386-140">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="b0386-141">**Workflow wurde erfolgreich abgeschlossen, mit dem Status: Wurde abgebrochen.**</span><span class="sxs-lookup"><span data-stu-id="b0386-141">**Workflow completed successfully with status: Canceled.**</span></span>    
### <a name="cancellation-and-compensableactivity"></a><span data-ttu-id="b0386-142">Abbruch und CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="b0386-142">Cancellation and CompensableActivity</span></span>  
 <span data-ttu-id="b0386-143">Wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> eines <xref:System.Activities.Statements.CompensableActivity>-Objekts nicht abgeschlossen wurden und die Aktivität abgebrochen wird, werden die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0386-143">If the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of a <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled, the activities in the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> are executed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0386-144"><xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> wird nur aufgerufen, wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> des <xref:System.Activities.Statements.CompensableActivity>-Objekts nicht abgeschlossen wurden und die Aktivität abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="b0386-144">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is only invoked if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have not completed and the activity is canceled.</span></span> <span data-ttu-id="b0386-145"><xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> wird nur ausgeführt, wenn die Aktivitäten in <xref:System.Activities.Statements.CompensableActivity.Body%2A> des <xref:System.Activities.Statements.CompensableActivity>-Objekts erfolgreich abgeschlossen wurden, und die Kompensation wird anschließend für die Aktivität aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0386-145">The <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> is only executed if the activities in the <xref:System.Activities.Statements.CompensableActivity.Body%2A> of the <xref:System.Activities.Statements.CompensableActivity> have successfully completed and compensation is subsequently invoked on the activity.</span></span>  
  
 <span data-ttu-id="b0386-146"><xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gibt Workflowautoren die Gelegenheit, eine geeignete Abbruchlogik bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b0386-146">The <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> gives workflow authors the opportunity to provide any appropriate cancellation logic.</span></span> <span data-ttu-id="b0386-147">Im folgenden Beispiel wird eine Ausnahme während der Ausführung von <xref:System.Activities.Statements.CompensableActivity.Body%2A> ausgelöst, und dann wird <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0386-147">In the following example, an exception is thrown during the execution of the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, and then the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> is invoked.</span></span>  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 <span data-ttu-id="b0386-148">Dieses Beispiel ist der Workflow in XAML.</span><span class="sxs-lookup"><span data-stu-id="b0386-148">This example is the workflow in XAML</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 <span data-ttu-id="b0386-149">Wenn der Workflow aufgerufen wird, wird die simulierte Fehlerbedingungsausnahme von der Hostanwendung in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> behandelt, der Workflow wird abgebrochen, und die Abbruchlogik von <xref:System.Activities.Statements.CompensableActivity> wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0386-149">When the workflow is invoked, the simulated error condition exception is handled by the host application in <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, the workflow is canceled, and the cancellation logic of the <xref:System.Activities.Statements.CompensableActivity> is invoked.</span></span> <span data-ttu-id="b0386-150">In diesem Beispiel haben die Kompensationslogik und die Abbruchlogik unterschiedliche Ziele.</span><span class="sxs-lookup"><span data-stu-id="b0386-150">In this example, the compensation logic and the cancellation logic have different goals.</span></span> <span data-ttu-id="b0386-151">Wenn <xref:System.Activities.Statements.CompensableActivity.Body%2A> erfolgreich abgeschlossen wurde, bedeutet dies, dass die Kreditkarte belastet und der Flug gebucht wurde. Somit sollten von der Kompensation beide Schritte rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b0386-151">If the <xref:System.Activities.Statements.CompensableActivity.Body%2A> completed successfully, then this means the credit card was charged and the flight booked, so the compensation should undo both steps.</span></span> <span data-ttu-id="b0386-152">(In diesem Beispiel wird durch den stornierten Flug automatisch die Kreditkartenbelastung storniert.) Wenn jedoch <xref:System.Activities.Statements.CompensableActivity> abgebrochen wird, bedeutet dies, dass <xref:System.Activities.Statements.CompensableActivity.Body%2A> nicht abgeschlossen wurde und damit die Logik von <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> in der Lage sein muss, zu bestimmen, wie der Abbruch am besten verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b0386-152">(In this example, canceling the flight automatically cancels the credit card charges.) However, if the <xref:System.Activities.Statements.CompensableActivity> is canceled, this means the <xref:System.Activities.Statements.CompensableActivity.Body%2A> did not complete and so the logic of the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> needs to be able to determine how to best handle the cancellation.</span></span> <span data-ttu-id="b0386-153">In diesem Beispiel wird die Kreditkartenbelastung durch <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> storniert. Da `ReserveFlight` jedoch die letzte Aktivität in <xref:System.Activities.Statements.CompensableActivity.Body%2A> war, wird nicht versucht, den Flug zu stornieren.</span><span class="sxs-lookup"><span data-stu-id="b0386-153">In this example, the <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> cancels the credit card charge, but since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, it does not attempt to cancel the flight.</span></span> <span data-ttu-id="b0386-154">`ReserveFlight` war die letzte Aktivität in <xref:System.Activities.Statements.CompensableActivity.Body%2A>. Wenn diese erfolgreich abgeschlossen worden wäre, wäre <xref:System.Activities.Statements.CompensableActivity.Body%2A> abgeschlossen worden und kein Abbruch möglich gewesen.</span><span class="sxs-lookup"><span data-stu-id="b0386-154">Since `ReserveFlight` was the last activity in the <xref:System.Activities.Statements.CompensableActivity.Body%2A>, if it had successfully completed then the <xref:System.Activities.Statements.CompensableActivity.Body%2A> would have completed and no cancellation would be possible.</span></span>  
  
 <span data-ttu-id="b0386-155">**ChargeCreditCard: Belastung der Kreditkarte für Flug.**</span><span class="sxs-lookup"><span data-stu-id="b0386-155">**ChargeCreditCard: Charge credit card for flight.**</span></span>  
<span data-ttu-id="b0386-156">**SimulatedErrorCondition: Auslösen von ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="b0386-156">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="b0386-157">**Nicht behandelte Workflowausnahme:** </span><span class="sxs-lookup"><span data-stu-id="b0386-157">**Workflow Unhandled Exception:** </span></span>  
<span data-ttu-id="b0386-158">**System.ApplicationException: Simulierte fehlerbedingung im Workflow.** </span><span class="sxs-lookup"><span data-stu-id="b0386-158">**System.ApplicationException: Simulated error condition in the workflow.** </span></span>  
<span data-ttu-id="b0386-159">**CancelCreditCard: Stornieren Sie kreditkartenbelastung.** </span><span class="sxs-lookup"><span data-stu-id="b0386-159">**CancelCreditCard: Cancel credit card charges.** </span></span>  
<span data-ttu-id="b0386-160">**Workflow wurde erfolgreich abgeschlossen, mit dem Status: Wurde abgebrochen.**</span><span class="sxs-lookup"><span data-stu-id="b0386-160">**Workflow completed successfully with status: Canceled.**</span></span>  <span data-ttu-id="b0386-161">Weitere Informationen über Abbrüche finden Sie unter [Abbruch](modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="b0386-161">For more information about cancellation, see [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a><span data-ttu-id="b0386-162">Explizite Kompensation mit Verwendung der Compensate-Aktivität</span><span class="sxs-lookup"><span data-stu-id="b0386-162">Explicit Compensation Using the Compensate Activity</span></span>  
 <span data-ttu-id="b0386-163">Im vorherigen Abschnitt wurde die implizite Kompensation behandelt.</span><span class="sxs-lookup"><span data-stu-id="b0386-163">In the previous section, implicit compensation was covered.</span></span> <span data-ttu-id="b0386-164">Eine implizite Kompensation eignet sich für einfache Szenarien. Wenn jedoch mehr explizite Steuerungsmöglichkeiten für das Planen der Kompensationsbehandlung erforderlich sind, kann die <xref:System.Activities.Statements.Compensate>-Aktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0386-164">Implicit compensation can be appropriate for simple scenarios, but if more explicit control is required over the scheduling of compensation handling then the <xref:System.Activities.Statements.Compensate> activity can be used.</span></span> <span data-ttu-id="b0386-165">Um den Kompensationsprozess mit der <xref:System.Activities.Statements.Compensate>-Aktivität zu initiieren, wird das <xref:System.Activities.Statements.CompensationToken>-Objekt des <xref:System.Activities.Statements.CompensableActivity>-Objekts verwendet, für das eine Kompensation möglich sein soll.</span><span class="sxs-lookup"><span data-stu-id="b0386-165">To initiate the compensation process with the <xref:System.Activities.Statements.Compensate> activity, the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> for which compensation is desired is used.</span></span> <span data-ttu-id="b0386-166">Mit der <xref:System.Activities.Statements.Compensate>-Aktivität kann eine Kompensation für ein beliebiges abgeschlossenes <xref:System.Activities.Statements.CompensableActivity>-Objekt initiiert werden, solange dieses nicht bestätigt oder kompensiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b0386-166">The <xref:System.Activities.Statements.Compensate> activity can be used to initiate compensation on any completed <xref:System.Activities.Statements.CompensableActivity> that has not been confirmed or compensated.</span></span> <span data-ttu-id="b0386-167">Beispielsweise kann eine <xref:System.Activities.Statements.Compensate>-Aktivität im Abschnitt <xref:System.Activities.Statements.TryCatch.Catches%2A> einer <xref:System.Activities.Statements.TryCatch>-Aktivität oder jederzeit nach Abschluss von <xref:System.Activities.Statements.CompensableActivity> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0386-167">For example, a <xref:System.Activities.Statements.Compensate> activity could be used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity, or any time after the <xref:System.Activities.Statements.CompensableActivity> has completed.</span></span> <span data-ttu-id="b0386-168">In diesem Beispiel wird die <xref:System.Activities.Statements.Compensate>-Aktivität im Abschnitt <xref:System.Activities.Statements.TryCatch.Catches%2A> einer <xref:System.Activities.Statements.TryCatch>-Aktivität dazu verwendet, die Aktion von <xref:System.Activities.Statements.CompensableActivity> rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="b0386-168">In this example, the <xref:System.Activities.Statements.Compensate> activity is used in the <xref:System.Activities.Statements.TryCatch.Catches%2A> section of a <xref:System.Activities.Statements.TryCatch> activity to reverse the action of the <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 <span data-ttu-id="b0386-169">Dieses Beispiel ist der Workflow in XAML.</span><span class="sxs-lookup"><span data-stu-id="b0386-169">This example is the workflow in XAML.</span></span>  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 <span data-ttu-id="b0386-170">Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-170">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="b0386-171">**ReserveFlight: Ticket wird reserviert.**</span><span class="sxs-lookup"><span data-stu-id="b0386-171">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="b0386-172">**SimulatedErrorCondition: Auslösen von ApplicationException.** </span><span class="sxs-lookup"><span data-stu-id="b0386-172">**SimulatedErrorCondition: Throwing an ApplicationException.** </span></span>  
<span data-ttu-id="b0386-173">**CancelFlight: Ticket wird storniert.** </span><span class="sxs-lookup"><span data-stu-id="b0386-173">**CancelFlight: Ticket is canceled.** </span></span>  
<span data-ttu-id="b0386-174">**Workflow wurde erfolgreich abgeschlossen, mit dem Status: Geschlossen.**</span><span class="sxs-lookup"><span data-stu-id="b0386-174">**Workflow completed successfully with status: Closed.**</span></span>    
### <a name="confirming-compensation"></a><span data-ttu-id="b0386-175">Bestätigen einer Kompensation</span><span class="sxs-lookup"><span data-stu-id="b0386-175">Confirming Compensation</span></span>  
 <span data-ttu-id="b0386-176">Standardmäßig können kompensierbare Aktivitäten jederzeit kompensiert werden, nachdem sie abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="b0386-176">By default, compensable activities can be compensated any time after they have completed.</span></span> <span data-ttu-id="b0386-177">Für einige Szenarien eignet sich diese Vorgehensweise möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="b0386-177">In some scenarios this may not be appropriate.</span></span> <span data-ttu-id="b0386-178">Im vorherigen Beispiel bestand die Kompensation bei der Reservierung des Tickets darin, den Reservierungsvorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="b0386-178">In the previous example the compensation to reserving the ticket was to cancel the reservation.</span></span> <span data-ttu-id="b0386-179">Nachdem der Flug jedoch stattgefunden hat, ist dieser Kompensationsschritt nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="b0386-179">However, after the flight has been completed this compensation step is no longer valid.</span></span> <span data-ttu-id="b0386-180">Bei der Bestätigung der kompensierbaren Aktivität wird die Aktivität aufgerufen, die von <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b0386-180">Confirming the compensable activity invokes the activity specified by the <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.</span></span> <span data-ttu-id="b0386-181">Eine Verwendungsmöglichkeit dafür besteht darin, alle Ressourcen freizugeben, die für die Durchführung der Kompensation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b0386-181">One possible use for this is to allow any resources that are necessary to perform the compensation to be released.</span></span> <span data-ttu-id="b0386-182">Nachdem eine kompensierbare Aktivität bestätigt wurde, kann sie nicht mehr kompensiert werden. Falls dies dennoch versucht wird, wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b0386-182">After a compensable activity is confirmed it is not possible for it to be compensated, and if this is attempted an <xref:System.InvalidOperationException> exception is thrown.</span></span> <span data-ttu-id="b0386-183">Wenn ein Workflow erfolgreich abgeschlossen wird, werden alle nicht bestätigten und nicht kompensierbaren Aktivitäten, die erfolgreich abgeschlossen wurden, in umgekehrter Reihenfolge Ihres Abschlusses bestätigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-183">When a workflow completes successfully, all non-confirmed and non-compensated compensable activities that completed successfully are confirmed in reverse order of completion.</span></span> <span data-ttu-id="b0386-184">In diesem Beispiel wird der Flug reserviert, gebucht und abgeschlossen, und dann wird die kompensierbare Aktivität bestätigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-184">In this example the flight is reserved, purchased, and completed, and then the compensable activity is confirmed.</span></span> <span data-ttu-id="b0386-185">Um ein <xref:System.Activities.Statements.CompensableActivity>-Objekt zu bestätigen, verwenden Sie die <xref:System.Activities.Statements.Confirm>-Aktivität, und geben Sie das <xref:System.Activities.Statements.CompensationToken>-Objekt des <xref:System.Activities.Statements.CompensableActivity>-Objekts an, das bestätigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0386-185">To confirm a <xref:System.Activities.Statements.CompensableActivity>, use the <xref:System.Activities.Statements.Confirm> activity and specify the <xref:System.Activities.Statements.CompensationToken> of the <xref:System.Activities.Statements.CompensableActivity> to confirm.</span></span>  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 <span data-ttu-id="b0386-186">Dieses Beispiel ist der Workflow in XAML.</span><span class="sxs-lookup"><span data-stu-id="b0386-186">This example is the workflow in XAML.</span></span>  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
<span data-ttu-id="b0386-187">Wenn der Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-187">When the workflow is invoked, the following output is displayed to the console.</span></span>  
  
<span data-ttu-id="b0386-188">**ReserveFlight: Ticket wird reserviert.**</span><span class="sxs-lookup"><span data-stu-id="b0386-188">**ReserveFlight: Ticket is reserved.**</span></span>  
<span data-ttu-id="b0386-189">**ManagerApproval: Manager-Genehmigung erhalten.** </span><span class="sxs-lookup"><span data-stu-id="b0386-189">**ManagerApproval: Manager approval received.** </span></span>  
<span data-ttu-id="b0386-190">**PurchaseFlight: Ticket wird gekauft.** </span><span class="sxs-lookup"><span data-stu-id="b0386-190">**PurchaseFlight: Ticket is purchased.** </span></span>  
<span data-ttu-id="b0386-191">**TakeFlight: Flug wird abgeschlossen.** </span><span class="sxs-lookup"><span data-stu-id="b0386-191">**TakeFlight: Flight is completed.** </span></span>  
<span data-ttu-id="b0386-192">**ConfirmFlight: Flug wurde angetreten, keine Kompensation möglich.** </span><span class="sxs-lookup"><span data-stu-id="b0386-192">**ConfirmFlight: Flight has been taken, no compensation possible.** </span></span>  
<span data-ttu-id="b0386-193">**Workflow wurde erfolgreich abgeschlossen, mit dem Status: Geschlossen.**</span><span class="sxs-lookup"><span data-stu-id="b0386-193">**Workflow completed successfully with status: Closed.**</span></span>   

## <a name="nesting-compensation-activities"></a><span data-ttu-id="b0386-194">Schachteln von Kompensationsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="b0386-194">Nesting Compensation Activities</span></span>  

<span data-ttu-id="b0386-195">Ein <xref:System.Activities.Statements.CompensableActivity>-Objekt kann in den Abschnitt <xref:System.Activities.Statements.CompensableActivity.Body%2A> eines anderen <xref:System.Activities.Statements.CompensableActivity>-Objekts eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b0386-195">A <xref:System.Activities.Statements.CompensableActivity> can be placed into the <xref:System.Activities.Statements.CompensableActivity.Body%2A> section of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="b0386-196"><xref:System.Activities.Statements.CompensableActivity> darf nicht in einen Handler einer anderen <xref:System.Activities.Statements.CompensableActivity> eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b0386-196">A <xref:System.Activities.Statements.CompensableActivity> may not be placed into a handler of another <xref:System.Activities.Statements.CompensableActivity>.</span></span> <span data-ttu-id="b0386-197">Eine übergeordnete <xref:System.Activities.Statements.CompensableActivity> muss dafür sorgen, dass im Falle eines Abbruchs, einer Bestätigung oder Kompensation alle untergeordneten kompensierbaren Aktivitäten, die erfolgreich abgeschlossen und noch nicht bestätigt oder kompensiert wurden, bestätigt oder kompensiert werden, bevor die übergeordnete Aktivität den Abbruch, die Bestätigung oder Kompensation abschließt.</span><span class="sxs-lookup"><span data-stu-id="b0386-197">It is the responsibility of a parent <xref:System.Activities.Statements.CompensableActivity> to ensure that when it is canceled, confirmed, or compensated, all child compensable activities that have completed successfully and have not already been confirmed or compensated must be confirmed or compensated before the parent completes cancellation, confirmation, or compensation.</span></span> <span data-ttu-id="b0386-198">Wenn dies nicht explizit modelliert wird, kompensiert die übergeordnete <xref:System.Activities.Statements.CompensableActivity> implizit untergeordnete kompensierbare Aktivitäten, wenn sie das Abbruch- oder Kompensationssignal empfängt.</span><span class="sxs-lookup"><span data-stu-id="b0386-198">If this is not modeled explicitly the parent <xref:System.Activities.Statements.CompensableActivity> will implicitly compensate child compensable activities if the parent received the cancel or compensate signal.</span></span> <span data-ttu-id="b0386-199">Nachdem die übergeordnete Aktivität das Bestätigungssignal empfangen hat, bestätigt sie implizit untergeordnete kompensierbare Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="b0386-199">If the parent received the confirm signal the parent will implicitly confirm child compensable activities.</span></span> <span data-ttu-id="b0386-200">Wenn die Logik zur Behandlung des Abbruchs, der Bestätigung oder Kompensation explizit im Handler der übergeordneten <xref:System.Activities.Statements.CompensableActivity> modelliert wird, wird jede untergeordnete Aktivität, die nicht explizit behandelt wird, implizit bestätigt.</span><span class="sxs-lookup"><span data-stu-id="b0386-200">If the logic to handle cancellation, confirmation, or compensation is explicitly modeled in the handler of the parent <xref:System.Activities.Statements.CompensableActivity>, any child not explicitly handled will be implicitly confirmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0386-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0386-201">See also</span></span>

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
