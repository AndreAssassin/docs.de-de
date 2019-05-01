---
title: Registrierungstool für Workflow Services (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 3ea0f737cc050ec3f918044e0e105a41011a3e25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052572"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="149c4-102">Registrierungstool für Workflow Services (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="149c4-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="149c4-103">Beim Registrierungstool für Workflow Services (WFServicesReg.exe) handelt es sich um ein eigenständiges Tool zum Hinzufügen, Entfernen oder Reparieren der Konfigurationselemente für Windows Workflow Foundation (WF)-Dienste.</span><span class="sxs-lookup"><span data-stu-id="149c4-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="149c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="149c4-104">Syntax</span></span>  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="149c4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="149c4-105">Remarks</span></span>  
 <span data-ttu-id="149c4-106">Das Tool befindet sich im Installationsverzeichnis von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Ausführlicher Pfad: %windir%\Microsoft.NET\Framework\v3.5 oder (auf 64-Bit-Computern) unter %windir%\Microsoft.NET\Framework64\v3.5.</span><span class="sxs-lookup"><span data-stu-id="149c4-106">The tool can be found at the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="149c4-107">In den folgenden Tabellen werden die Optionen beschrieben, die mit dem Registrierungstool für Workflow Services (WFServicesReg.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="149c4-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="149c4-108">Option</span><span class="sxs-lookup"><span data-stu-id="149c4-108">Option</span></span>|<span data-ttu-id="149c4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="149c4-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="149c4-110">Dient zum Konfigurieren von Windows Workflow Services.</span><span class="sxs-lookup"><span data-stu-id="149c4-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="149c4-111">Wird zum Installieren und Reparieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="149c4-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="149c4-112">Entfernt die Konfiguration von Windows Workflow Services.</span><span class="sxs-lookup"><span data-stu-id="149c4-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="149c4-113">Druckt ausführliche Informationen (entweder für die Konfiguration oder für das Löschen).</span><span class="sxs-lookup"><span data-stu-id="149c4-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="149c4-114">Aktiviert das MSI-Protokollierungsformat.</span><span class="sxs-lookup"><span data-stu-id="149c4-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="149c4-115">Minimiert das Fenster, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="149c4-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="149c4-116">Registrierung</span><span class="sxs-lookup"><span data-stu-id="149c4-116">Registration</span></span>  
 <span data-ttu-id="149c4-117">Die Datei Web.config wird untersucht. Dabei wird Folgendes registriert:</span><span class="sxs-lookup"><span data-stu-id="149c4-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]<span data-ttu-id="149c4-118">-Referenzassemblys</span><span class="sxs-lookup"><span data-stu-id="149c4-118">reference assemblies.</span></span>  
  
- <span data-ttu-id="149c4-119">Ein Buildanbieter für XOML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="149c4-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="149c4-120">HTTP-Handler für XOML- und RULES-Dateien.</span><span class="sxs-lookup"><span data-stu-id="149c4-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="149c4-121">Die Datei Machine.config wird untersucht. Dabei werden die folgenden Erweiterungen registriert:</span><span class="sxs-lookup"><span data-stu-id="149c4-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="149c4-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="149c4-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="149c4-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="149c4-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="149c4-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="149c4-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="149c4-125">Des Weiteren werden die folgenden Importprogramme für Clientmetadaten registriert:</span><span class="sxs-lookup"><span data-stu-id="149c4-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="149c4-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="149c4-126">policyImporters</span></span>  
  
- <span data-ttu-id="149c4-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="149c4-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="149c4-128">Auch XOML und RULES-Skriptzuordnungen und -Handler werden in der IIS-Metabasis registriert.</span><span class="sxs-lookup"><span data-stu-id="149c4-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="149c4-129">Auf Computern unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../includes/wxp-md.md)] (IIS&amp;#160;5.1 oder [!INCLUDE[iis601](../../../includes/iis601-md.md)]) wird ein XOML- und RULES-Skriptzuordnungssatz registriert.</span><span class="sxs-lookup"><span data-stu-id="149c4-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and [!INCLUDE[iis601](../../../includes/iis601-md.md)]), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="149c4-130">Auf 64-Bit-Computern werden bei aktiviertem `Enable32BitAppOnWin64`-Schalter WOW-Modus-Skriptzuordnungen registriert, bei aktiviertem `Enable32BitAppOnWin64`-Schalter werden systemeigene 64-Bit-Skriptzuordnungen registriert.</span><span class="sxs-lookup"><span data-stu-id="149c4-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="149c4-131">Auf [!INCLUDE[wv](../../../includes/wv-md.md)] und Windows Server 2008 (IIS 7.0 und höher) zwei Sätze von xoml-und Rules-Computern registriert sind: eine für den integrierten und einer für den klassischen Modus.</span><span class="sxs-lookup"><span data-stu-id="149c4-131">On [!INCLUDE[wv](../../../includes/wv-md.md)] and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="149c4-132">Auf 64-Bit-Computern werden drei Handlersätze registriert (unabhängig vom Zustand des `Enable32BitAppOnWin64`-Schalters): einer für den integrierten Modus, einer für den klassischen WOW-Modus und einer für den systemeigenen klassischen 64-Bit-Modus.</span><span class="sxs-lookup"><span data-stu-id="149c4-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="149c4-133">Im Gegensatz zu ServiceModelreg.exe ist es bei WFServicesReg.exe nicht zulässig, Skriptzuordnungen oder Handler für eine bestimmte Website hinzuzufügen, zu entfernen oder zu reparieren.</span><span class="sxs-lookup"><span data-stu-id="149c4-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="149c4-134">Eine Möglichkeit zum Umgehen dieses Problems finden Sie im Abschnitt "Reparieren der Skriptzuordnungen".</span><span class="sxs-lookup"><span data-stu-id="149c4-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="149c4-135">Verwendungsszenarien</span><span class="sxs-lookup"><span data-stu-id="149c4-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="149c4-136">Installieren von IIS, nachdem .NET Framework&amp;#160;3.5 installiert wurde</span><span class="sxs-lookup"><span data-stu-id="149c4-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="149c4-137">Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] vor IIS installiert.</span><span class="sxs-lookup"><span data-stu-id="149c4-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed prior to IIS installation.</span></span> <span data-ttu-id="149c4-138">Da die IIS-Metabasis nicht verfügbar ist, ist die Installation von [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] ohne Installation von XOML- und RULES-Skriptzuordnungen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="149c4-138">Due to the unavailability of the IIS metabase, installation of [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="149c4-139">Verwenden Sie nach der Installation von IIS das Tool WFServicesReg.exe mit dem `/c`-Schalter, um diese Skriptzuordnungen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="149c4-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="149c4-140">Reparieren der Skriptzuordnungen</span><span class="sxs-lookup"><span data-stu-id="149c4-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="149c4-141">Gelöschte Skriptzuordnung des Knotens "Websites"</span><span class="sxs-lookup"><span data-stu-id="149c4-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="149c4-142">Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES versehentlich aus dem Websites-Knoten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="149c4-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="149c4-143">Dies lässt sich durch Ausführen des Tools WFServicesReg.exe mit dem `/c`-Schalter reparieren.</span><span class="sxs-lookup"><span data-stu-id="149c4-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="149c4-144">Gelöschte Skriptzuordnung einer bestimmten Website</span><span class="sxs-lookup"><span data-stu-id="149c4-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="149c4-145">Auf einem Computer unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wurde XOML oder RULES nicht aus dem Websites-Knoten, sondern versehentlich aus einer bestimmten Website (beispielsweise der Standardwebsite) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="149c4-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="149c4-146">Führen Sie zum Reparieren der gelöschten Handler einer bestimmten Website "WFServicesReg.exe/r" führen Sie "WFServicesReg.exe/c", um Handler von allen Websites zu entfernen, um die entsprechenden Handler für alle Websites zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="149c4-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="149c4-147">Konfigurieren von Handlern nach Wechseln des IIS-Modus</span><span class="sxs-lookup"><span data-stu-id="149c4-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="149c4-148">Befindet sich IIS im freigegebenen Konfigurationsmodus und ist [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installiert, wird die IIS-Metabasis an einem freigegebenen Speicherort konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="149c4-148">When IIS is in shared configuration mode and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="149c4-149">Wird für IIS zum nicht freigegebenen Konfigurationsmodus gewechselt, sind die erforderlichen Handler nicht in der lokalen Metabasis vorhanden.</span><span class="sxs-lookup"><span data-stu-id="149c4-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="149c4-150">Um die lokale Metabasis ordnungsgemäß zu konfigurieren, können Sie entweder die freigegebene Metabasis lokal, oder führen "WFServicesReg.exe/c", die die lokale Metabasis konfiguriert importieren.</span><span class="sxs-lookup"><span data-stu-id="149c4-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
