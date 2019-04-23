---
title: < System.diagnostics >-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142706"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="282f5-102">\<System.Diagnostics >-Element</span><span class="sxs-lookup"><span data-stu-id="282f5-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="282f5-103">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="282f5-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="282f5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="282f5-104">\<configuration></span></span>  
<span data-ttu-id="282f5-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="282f5-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282f5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="282f5-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="282f5-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="282f5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="282f5-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="282f5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="282f5-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="282f5-109">Attributes</span></span>  
 <span data-ttu-id="282f5-110">Keine</span><span class="sxs-lookup"><span data-stu-id="282f5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="282f5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="282f5-111">Child Elements</span></span>  
  
|<span data-ttu-id="282f5-112">Element</span><span class="sxs-lookup"><span data-stu-id="282f5-112">Element</span></span>|<span data-ttu-id="282f5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="282f5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="282f5-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="282f5-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="282f5-115">Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="282f5-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="282f5-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="282f5-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="282f5-117">Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="282f5-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="282f5-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="282f5-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="282f5-119">Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="282f5-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="282f5-120">Listener, die als freigegebene Listener können anhand des Namens mit Quellen oder ablaufverfolgungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="282f5-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="282f5-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="282f5-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="282f5-122">Gibt die Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="282f5-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="282f5-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="282f5-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="282f5-124">Enthält Ablaufverfolgungsschalter und die Ebenen, wo die Ablaufverfolgungsschalter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="282f5-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="282f5-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="282f5-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="282f5-126">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="282f5-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="282f5-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="282f5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="282f5-128">Element</span><span class="sxs-lookup"><span data-stu-id="282f5-128">Element</span></span>|<span data-ttu-id="282f5-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="282f5-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="282f5-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="282f5-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="282f5-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="282f5-131">Example</span></span>  
 <span data-ttu-id="282f5-132">Das folgende Beispiel zeigt, wie Sie einen Ablaufverfolgungsschalter sowie eines Ablaufverfolgungslisteners in Einbetten der  **\<system.diagnostics >** Element.</span><span class="sxs-lookup"><span data-stu-id="282f5-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="282f5-133">Die `General` Ablaufverfolgungsschalter festgelegt ist, um die <xref:System.Diagnostics.TraceLevel> Ebene.</span><span class="sxs-lookup"><span data-stu-id="282f5-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="282f5-134">Der Ablaufverfolgungslistener `myListener` erstellt eine Datei namens `MyListener.log` und schreibt die Ausgabe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="282f5-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="282f5-135">In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="282f5-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="282f5-136">Sie können z. B. angeben `true` für eine <xref:System.Diagnostics.BooleanSwitch> oder verwenden Sie den Text, der einem Enumerationswert entspricht z. B. `Error` für eine <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="282f5-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="282f5-137">Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="282f5-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="282f5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="282f5-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="282f5-139">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="282f5-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
