---
title: <participants>von WCF
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: 44962c12f0c7260799d04f26b3fa16016edd2b7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932815"
---
# <a name="participants-of-wcf"></a><span data-ttu-id="efe89-102">\<Teilnehmer > von WCF</span><span class="sxs-lookup"><span data-stu-id="efe89-102">\<participants> of WCF</span></span>
<span data-ttu-id="efe89-103">Konfiguriert eine Liste von Nachverfolgungsteilnehmern, die den direkt von der Laufzeit ausgegebenen Nachverfolgungsdatensätzen lauschen und sie entsprechend der Weise verarbeiten, wie sie konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="efe89-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="efe89-104">Dies umfasst das Schreiben in ein bestimmtes Ausgabemedium (z. B. Datei, Konsole, ETW), das Verarbeiten/Aggregieren der Datensätze oder eine beliebige andere Kombination, die erforderlich sein könnte.</span><span class="sxs-lookup"><span data-stu-id="efe89-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="efe89-105">Weitere Informationen zur Workflow Nachverfolgung und Nachverfolgung von Teilnehmern finden Sie unter [Workflow Verfolgung und Ablauf](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) Verfolgung und nach [Verfolgung von Teilnehmern](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="efe89-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="efe89-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="efe89-106">\<system.serviceModel></span></span>  
<span data-ttu-id="efe89-107">\<Überwachungs ></span><span class="sxs-lookup"><span data-stu-id="efe89-107">\<tracking></span></span>  
<span data-ttu-id="efe89-108">\<Teilnehmer ></span><span class="sxs-lookup"><span data-stu-id="efe89-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe89-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="efe89-109">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efe89-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="efe89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efe89-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="efe89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efe89-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="efe89-112">Attributes</span></span>  
 <span data-ttu-id="efe89-113">Keine</span><span class="sxs-lookup"><span data-stu-id="efe89-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="efe89-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efe89-114">Child Elements</span></span>  
  
|<span data-ttu-id="efe89-115">Element</span><span class="sxs-lookup"><span data-stu-id="efe89-115">Element</span></span>|<span data-ttu-id="efe89-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe89-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efe89-117">\<add></span><span class="sxs-lookup"><span data-stu-id="efe89-117">\<add></span></span>](../windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="efe89-118">Enthält Einstellungen für einen Nachverfolgungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="efe89-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efe89-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efe89-119">Parent Elements</span></span>  
  
|<span data-ttu-id="efe89-120">Element</span><span class="sxs-lookup"><span data-stu-id="efe89-120">Element</span></span>|<span data-ttu-id="efe89-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe89-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efe89-122">\<tracking></span><span class="sxs-lookup"><span data-stu-id="efe89-122">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="efe89-123">Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.</span><span class="sxs-lookup"><span data-stu-id="efe89-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efe89-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="efe89-124">Remarks</span></span>  
 <span data-ttu-id="efe89-125">Nachverfolgungsteilnehmer werden verwendet, um die vom Workflow ausgegebenen Nachverfolgungsdaten zu erfassen und in verschiedenen Medien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="efe89-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="efe89-126">Außerdem kann jede Nachverarbeitung der Nachverfolgungsdatensätze auch innerhalb des Nachverfolgungsteilnehmers erfolgen.</span><span class="sxs-lookup"><span data-stu-id="efe89-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="efe89-127">Die Nachverfolgungsereignisse können von mehreren Nachverfolgungsteilnehmern gleichzeitig verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="efe89-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="efe89-128">Jedem Nachverfolgungsteilnehmer kann ein anderes Nachverfolgungsprofil zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="efe89-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="efe89-129">Standardmäßig wird ein Nachverfolgungsteilnehmer bereitgestellt, der die Nachverfolgungsdatensätze in eine ETW-Sitzung schreibt.</span><span class="sxs-lookup"><span data-stu-id="efe89-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="efe89-130">Der Teilnehmer wird für einen Workflowdienst konfiguriert, indem einer Konfigurationsdatei ein nachverfolgungsspezifisches Verhalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="efe89-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="efe89-131">Durch Aktivierung eines ETW-Nachverfolgungsteilnehmers können Nachverfolgungsdatensätze in der Ereignisanzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="efe89-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="efe89-132">Wenn dies nicht Ihren Anforderungen entspricht, können Sie auch einen benutzerdefinierten Überwachungsteilnehmer schreiben.</span><span class="sxs-lookup"><span data-stu-id="efe89-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efe89-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="efe89-133">Example</span></span>  
 <span data-ttu-id="efe89-134">In der folgenden Beispielkonfiguration wird der standardmäßige ETW-Nachverfolgungsteilnehmer gezeigt, der in der Datei Web.config konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="efe89-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="efe89-135">Die Anbieter-ID, die der ETW-Nachverfolgungsteilnehmer verwendet, um die Nachverfolgungsdatensätze an ETW weiterzuleiten, ist im Abschnitt `<diagnostics>` definiert.</span><span class="sxs-lookup"><span data-stu-id="efe89-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="efe89-136">Dem Nachverfolgungsteilnehmer ist ein Profil zugeordnet, das die Nachverfolgungsdatensätze angibt, die er abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="efe89-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="efe89-137">Dieses Profil wird durch das `profileName`-Attribut des `<add>`-Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="efe89-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="efe89-138">Sobald alles definiert ist, wird der Nachverfolgungsteilnehmer dem `<etwTracking>`-Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="efe89-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="efe89-139">Dadurch wird der ausgewählte Nachverfolgungsteilnehmer den Erweiterungen der Workflowinstanz hinzugefügt, die daraufhin die Nachverfolgungsdatensätze empfangen.</span><span class="sxs-lookup"><span data-stu-id="efe89-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="efe89-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efe89-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="efe89-141">Nachverfolgung und Ablaufverfolgung für Workflows</span><span class="sxs-lookup"><span data-stu-id="efe89-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="efe89-142">Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="efe89-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
