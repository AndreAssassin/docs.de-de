---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 539ce0ba72ae7a8d568cdea3a1a3aab3eec1001b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790389"
---
# <a name="activitystatequery"></a><span data-ttu-id="816e9-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="816e9-101">\<activityStateQuery></span></span>
<span data-ttu-id="816e9-102">Stellt eine Abfrage dar, die verwendet wird, um Lebenszyklusänderungen der Aktivitäten nachzuverfolgen, die zu einer Workflowinstanz gehören.</span><span class="sxs-lookup"><span data-stu-id="816e9-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="816e9-103">Beispielsweise empfiehlt es sich zum Nachverfolgen jedes Mal, wenn die Aktivität "E-Mail senden" innerhalb einer Workflowinstanz abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="816e9-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="816e9-104">Diese Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte des Aktivitätszustands abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="816e9-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="816e9-105">Die verfügbaren Zustände, die abonniert werden können, sind in ActivityStates angegeben.</span><span class="sxs-lookup"><span data-stu-id="816e9-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="816e9-106">Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="816e9-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="816e9-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="816e9-107">\<system.serviceModel></span></span>  
<span data-ttu-id="816e9-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="816e9-108">\<tracking></span></span>  
<span data-ttu-id="816e9-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="816e9-109">\<trackingProfile></span></span>  
<span data-ttu-id="816e9-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="816e9-110">\<workflow></span></span>  
<span data-ttu-id="816e9-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="816e9-111">\<activityStateQueries></span></span>  
<span data-ttu-id="816e9-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="816e9-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816e9-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="816e9-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="816e9-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="816e9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="816e9-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="816e9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="816e9-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="816e9-116">Attributes</span></span>  
  
|<span data-ttu-id="816e9-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="816e9-117">Attribute</span></span>|<span data-ttu-id="816e9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="816e9-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="816e9-119">activityName</span><span class="sxs-lookup"><span data-stu-id="816e9-119">activityName</span></span>|<span data-ttu-id="816e9-120">Eine Zeichenfolge, die den Namen der Aktivität angibt, für die <xref:System.Activities.Tracking.ActivityStateRecord>-Instanzen gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="816e9-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="816e9-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="816e9-121">Child Elements</span></span>  
  
|<span data-ttu-id="816e9-122">Element</span><span class="sxs-lookup"><span data-stu-id="816e9-122">Element</span></span>|<span data-ttu-id="816e9-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="816e9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="816e9-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="816e9-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="816e9-125">Eine Auflistung der dieser Aktivitätsabfrage zugeordneten Argumente.</span><span class="sxs-lookup"><span data-stu-id="816e9-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="816e9-126">\<states></span><span class="sxs-lookup"><span data-stu-id="816e9-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="816e9-127">Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="816e9-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="816e9-128">\<states></span><span class="sxs-lookup"><span data-stu-id="816e9-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="816e9-129">Eine Auflistung von Variablen, die dieser Aktivitätsabfrage zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="816e9-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="816e9-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="816e9-130">Parent Elements</span></span>  
  
|<span data-ttu-id="816e9-131">Element</span><span class="sxs-lookup"><span data-stu-id="816e9-131">Element</span></span>|<span data-ttu-id="816e9-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="816e9-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="816e9-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="816e9-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="816e9-134">Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="816e9-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="816e9-135">Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.</span><span class="sxs-lookup"><span data-stu-id="816e9-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="816e9-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="816e9-136">Remarks</span></span>  
 <span data-ttu-id="816e9-137">Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="816e9-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="816e9-138">Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="816e9-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="816e9-139">Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elementen, die jede beliebige Variable oder ein Argument zu extrahieren. in einer beliebigen Aktivität in einem Workflow.</span><span class="sxs-lookup"><span data-stu-id="816e9-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="816e9-140">Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`-Überwachungsdatensatz der Aktivität ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="816e9-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="816e9-141">Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und daher abonniert werden innerhalb eines Überwachungsprofils profilerstellung mithilfe [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="816e9-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="816e9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="816e9-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="816e9-143">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="816e9-143">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="816e9-144">Überwachungsprofile</span><span class="sxs-lookup"><span data-stu-id="816e9-144">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
