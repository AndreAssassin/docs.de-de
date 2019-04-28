---
title: <trace>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 5faf352dce2a459a999b3cf54209f6bd9793bde0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673796"
---
# <a name="trace-element"></a><span data-ttu-id="b2e63-102">\<Ablaufverfolgung >-Element</span><span class="sxs-lookup"><span data-stu-id="b2e63-102">\<trace> Element</span></span>
<span data-ttu-id="b2e63-103">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b2e63-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="b2e63-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2e63-104">\<configuration></span></span>  
<span data-ttu-id="b2e63-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b2e63-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b2e63-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="b2e63-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e63-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2e63-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2e63-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e63-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2e63-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2e63-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2e63-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2e63-110">Attributes</span></span>  
  
|<span data-ttu-id="b2e63-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2e63-111">Attribute</span></span>|<span data-ttu-id="b2e63-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e63-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="b2e63-113">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b2e63-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b2e63-114">Gibt an, ob der Ablaufverfolgungslistener die Ausgabepuffer automatisch nach jedem Schreibvorgang geleert.</span><span class="sxs-lookup"><span data-stu-id="b2e63-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="b2e63-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b2e63-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b2e63-116">Gibt die Anzahl der Leerzeichen für den Einzug an.</span><span class="sxs-lookup"><span data-stu-id="b2e63-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="b2e63-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b2e63-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b2e63-118">Gibt an, ob die globale Sperre verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2e63-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="b2e63-119">AutoFlush-Attribut</span><span class="sxs-lookup"><span data-stu-id="b2e63-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="b2e63-120">Wert</span><span class="sxs-lookup"><span data-stu-id="b2e63-120">Value</span></span>|<span data-ttu-id="b2e63-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e63-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b2e63-122">Der Ausgabepuffer ist nicht automatisch geleert werden.</span><span class="sxs-lookup"><span data-stu-id="b2e63-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="b2e63-123">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b2e63-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b2e63-124">Automatisch leert den Ausgabepuffer.</span><span class="sxs-lookup"><span data-stu-id="b2e63-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="b2e63-125">UseGlobalLock-Attribut</span><span class="sxs-lookup"><span data-stu-id="b2e63-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="b2e63-126">Wert</span><span class="sxs-lookup"><span data-stu-id="b2e63-126">Value</span></span>|<span data-ttu-id="b2e63-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e63-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b2e63-128">Die globale Sperre wird nicht verwendet werden, wenn der Listener threadsicher ist. Andernfalls wird die globale Sperre verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2e63-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="b2e63-129">Verwendet die globale Sperre unabhängig davon, ob der Listener threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="b2e63-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="b2e63-130">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b2e63-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2e63-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e63-131">Child Elements</span></span>  
  
|<span data-ttu-id="b2e63-132">Element</span><span class="sxs-lookup"><span data-stu-id="b2e63-132">Element</span></span>|<span data-ttu-id="b2e63-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e63-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2e63-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b2e63-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="b2e63-135">Gibt an, einen Listener, der sammelt, speichert, und leitet Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b2e63-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2e63-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2e63-136">Parent Elements</span></span>  
  
|<span data-ttu-id="b2e63-137">Element</span><span class="sxs-lookup"><span data-stu-id="b2e63-137">Element</span></span>|<span data-ttu-id="b2e63-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2e63-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2e63-139">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b2e63-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b2e63-140">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b2e63-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2e63-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e63-141">Example</span></span>  
 <span data-ttu-id="b2e63-142">Das folgende Beispiel zeigt, wie Sie mit der `<trace>` Element, um den Listener hinzuzufügen `MyListener` auf die `Listeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b2e63-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="b2e63-143">`MyListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in der Datei.</span><span class="sxs-lookup"><span data-stu-id="b2e63-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="b2e63-144">Die `useGlobalLock` -Attributsatz auf `false`, der bewirkt, dass der globale Sperre nicht verwendet werden, wenn der Ablaufverfolgungslistener threadsicher ist.</span><span class="sxs-lookup"><span data-stu-id="b2e63-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="b2e63-145">Die `autoflush` -Attributsatz auf `true`, der bewirkt, dass die Ablaufverfolgungs-Listener Schreiben in die Datei unabhängig davon, ob die <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b2e63-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="b2e63-146">Die `indentsize` -Attributsatz auf 0 (null), wodurch den Listener für den Einzug der keine Leerzeichen bei der <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b2e63-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2e63-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2e63-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="b2e63-148">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b2e63-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
