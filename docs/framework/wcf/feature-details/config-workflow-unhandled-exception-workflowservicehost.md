---
title: 'Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: cd3729019b5371b5313bba3814758c723c0d448a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318745"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="ca031-102">Vorgehensweise: Konfigurieren des Verhaltens bei nicht behandelten Ausnahmen für Workflows mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="ca031-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="ca031-103">Das <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> ist ein Verhalten, über das Sie die Aktion angeben können, die ausgeführt wird, wenn eine nicht behandelte Ausnahme innerhalb eines unter <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflows auftritt.</span><span class="sxs-lookup"><span data-stu-id="ca031-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="ca031-104">In diesem Thema wird erläutert, wie Sie dieses Verhalten in einer Konfigurationsdatei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ca031-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="ca031-105">So konfigurieren Sie WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="ca031-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="ca031-106">Hinzufügen eine <`workflowUnhandledException`> Element in ein <`behavior`> Element innerhalb einer <`serviceBehaviors`>-Element, mit der `action` Attribut gibt die Aktion an, wenn eine nicht behandelte Ausnahme auftritt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca031-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ca031-107">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca031-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="ca031-108">Weitere Informationen finden Sie unter [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ca031-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="ca031-109">Dieses Verhalten kann im Code konfiguriert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca031-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="ca031-110">Die `action` -Attribut der <`workflowUnhandledException`>-Element kann auf einen der folgenden Werte festgelegt:</span><span class="sxs-lookup"><span data-stu-id="ca031-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     **<span data-ttu-id="ca031-111">abandon</span><span class="sxs-lookup"><span data-stu-id="ca031-111">abandon</span></span>**  
     <span data-ttu-id="ca031-112">Bricht die Instanz im Arbeitsspeicher ab, ohne den beibehaltenen Instanzzustand (also Rollback zum letzten Beibehaltungspunkt) zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ca031-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     **<span data-ttu-id="ca031-113">abandonAndSuspend</span><span class="sxs-lookup"><span data-stu-id="ca031-113">abandonAndSuspend</span></span>**  
     <span data-ttu-id="ca031-114">Bricht die Instanz im Arbeitsspeicher ab und aktualisiert die beibehaltene Instanz, die angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca031-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     **<span data-ttu-id="ca031-115">cancel</span><span class="sxs-lookup"><span data-stu-id="ca031-115">cancel</span></span>**  
     <span data-ttu-id="ca031-116">Ruft Abbruchhandler für die Instanz auf und schließt dann die Instanz im Arbeitsspeicher ab, wobei diese ggf. auch aus dem Instanzspeicher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ca031-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     **<span data-ttu-id="ca031-117">terminate</span><span class="sxs-lookup"><span data-stu-id="ca031-117">terminate</span></span>**  
     <span data-ttu-id="ca031-118">Schließt die Instanz im Arbeitsspeicher ab und entfernt diese aus dem Instanzspeicher.</span><span class="sxs-lookup"><span data-stu-id="ca031-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="ca031-119">Weitere Informationen zu <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, finden Sie unter [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="ca031-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca031-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca031-120">See also</span></span>

- [<span data-ttu-id="ca031-121">Erweiterbarkeit des Workflowdiensthosts</span><span class="sxs-lookup"><span data-stu-id="ca031-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="ca031-122">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="ca031-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
