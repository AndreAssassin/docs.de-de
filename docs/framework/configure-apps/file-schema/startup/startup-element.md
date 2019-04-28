---
title: <startup>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 5047cb0ab1c8206abd88dc795e50272d69f1fd3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701449"
---
# <a name="startup-element"></a><span data-ttu-id="b2e87-102">\<Startup >-Element</span><span class="sxs-lookup"><span data-stu-id="b2e87-102">\<startup> element</span></span>

<span data-ttu-id="b2e87-103">Gibt beim Start zur common Language Runtime an.</span><span class="sxs-lookup"><span data-stu-id="b2e87-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="b2e87-104">\<configuration> \<startup></span><span class="sxs-lookup"><span data-stu-id="b2e87-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="b2e87-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2e87-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2e87-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e87-106">Attributes and elements</span></span>

 <span data-ttu-id="b2e87-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2e87-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2e87-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2e87-108">Attributes</span></span>

|<span data-ttu-id="b2e87-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2e87-109">Attribute</span></span>|<span data-ttu-id="b2e87-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e87-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="b2e87-111">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b2e87-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b2e87-112">Gibt an, ob die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Richtlinie für die laufzeitaktivierung oder verwendet den [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Activation-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b2e87-112">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b2e87-113">useLegacyV2RuntimeActivationPolicy attribute</span><span class="sxs-lookup"><span data-stu-id="b2e87-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="b2e87-114">Wert</span><span class="sxs-lookup"><span data-stu-id="b2e87-114">Value</span></span>|<span data-ttu-id="b2e87-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e87-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="b2e87-116">Aktivieren Sie [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Runtime Activation-Richtlinie für die ausgewählte Runtime, die ältere Laufzeit Aktivierung Techniken gebunden ist (z. B. die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) zur Laufzeit ausgewählt wird, aus der Konfigurationsdatei anstelle von sodass sie an der CLR, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="b2e87-116">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="b2e87-117">Wenn CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, sind gemischte Assemblys, die mit früheren Versionen von .NET Framework erstellt daher mit der ausgewählten Version der CLR geladen.</span><span class="sxs-lookup"><span data-stu-id="b2e87-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="b2e87-118">Festlegen dieses Werts verhindert, dass CLR, Version 1.1 oder CLR-Version 2.0 in den gleichen Prozess, effektiv deaktivieren, die in-Process-Seite-an-Seite lädt.</span><span class="sxs-lookup"><span data-stu-id="b2e87-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="b2e87-119">Verwenden Sie die Standardrichtlinie für die Aktivierung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen, die auf ältere Laufzeit Activation-Verfahren, um die CLR, Version 1.1 oder 2.0 in den Prozess zu laden kann.</span><span class="sxs-lookup"><span data-stu-id="b2e87-119">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="b2e87-120">Wenn dieser Wert verhindert, dass im gemischten Modus Assemblys in .NET Framework 4 oder höher werden geladen, es sei denn, sie mit .NET Framework 4 oder höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b2e87-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="b2e87-121">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="b2e87-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b2e87-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e87-122">Child elements</span></span>

|<span data-ttu-id="b2e87-123">Element</span><span class="sxs-lookup"><span data-stu-id="b2e87-123">Element</span></span>|<span data-ttu-id="b2e87-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e87-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2e87-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="b2e87-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="b2e87-126">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2e87-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="b2e87-127">Anwendungen, die mit der Common Language RuntimeVersion 1.1 oder höher verwenden, sollte die  **\<SupportedRuntime >** Element.</span><span class="sxs-lookup"><span data-stu-id="b2e87-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="b2e87-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="b2e87-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="b2e87-129">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b2e87-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b2e87-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e87-130">Parent elements</span></span>

|<span data-ttu-id="b2e87-131">Element</span><span class="sxs-lookup"><span data-stu-id="b2e87-131">Element</span></span>|<span data-ttu-id="b2e87-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e87-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b2e87-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b2e87-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2e87-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2e87-134">Remarks</span></span>

 <span data-ttu-id="b2e87-135">Die  **\<SupportedRuntime >** Element sollte verwendet werden, von allen Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2e87-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="b2e87-136">Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die  **\<RequiredRuntime >** Element.</span><span class="sxs-lookup"><span data-stu-id="b2e87-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="b2e87-137">Der Startcode für eine in Microsoft Internet Explorer gehostete Anwendung ignoriert die  **\<Start >** -Element und seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="b2e87-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b2e87-138">Das Attribut useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="b2e87-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="b2e87-139">Dieses Attribut ist nützlich, wenn Ihre Anwendung legacy-Aktivierungspfade,, wie z. B. verwendet die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren möchten oder wenn Ihre Anwendung Dank der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] weist jedoch eine Abhängigkeit für eine gemischte-Assembly, die mit einer früheren Version von .NET Framework erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2e87-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="b2e87-140">In diesen Szenarien legen Sie das Attribut auf `true`.</span><span class="sxs-lookup"><span data-stu-id="b2e87-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="b2e87-141">Festlegen des Attributs auf `true` verhindert CLR, Version 1.1 oder CLR, Version 2.0 lädt in den gleichen Prozess, der effektiv den deaktivieren, in-Process Side-by-Side (finden Sie unter [Seite-an-Seite-Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="b2e87-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="b2e87-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e87-142">Example</span></span>

 <span data-ttu-id="b2e87-143">Das folgende Beispiel zeigt, wie die Runtime-Version in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b2e87-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b2e87-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2e87-144">See also</span></span>

- [<span data-ttu-id="b2e87-145">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b2e87-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b2e87-146">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b2e87-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b2e87-147">Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="b2e87-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="b2e87-148">[Seite-an-Seite-Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2e87-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="b2e87-149">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="b2e87-149">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)