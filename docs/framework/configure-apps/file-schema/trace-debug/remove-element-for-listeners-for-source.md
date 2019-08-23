---
title: <remove>-Element <listeners> für für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926991"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="b941c-102">\<Entfernen Sie > Element \<für Listener > \<für Quell ></span><span class="sxs-lookup"><span data-stu-id="b941c-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b941c-103">Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="b941c-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b941c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b941c-104">\<configuration></span></span>  
<span data-ttu-id="b941c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b941c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b941c-106">\<Quellen ></span><span class="sxs-lookup"><span data-stu-id="b941c-106">\<sources></span></span>  
<span data-ttu-id="b941c-107">\<Quell ></span><span class="sxs-lookup"><span data-stu-id="b941c-107">\<source></span></span>  
<span data-ttu-id="b941c-108">\<Listener ></span><span class="sxs-lookup"><span data-stu-id="b941c-108">\<listeners></span></span>  
<span data-ttu-id="b941c-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="b941c-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b941c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b941c-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b941c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b941c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b941c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b941c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b941c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b941c-113">Attributes</span></span>  
  
|<span data-ttu-id="b941c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b941c-114">Attribute</span></span>|<span data-ttu-id="b941c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b941c-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b941c-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b941c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b941c-117">Der Name des Listener, der aus der `Listeners` Auflistung entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b941c-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b941c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b941c-118">Child Elements</span></span>  
 <span data-ttu-id="b941c-119">Keine</span><span class="sxs-lookup"><span data-stu-id="b941c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b941c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b941c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b941c-121">Element</span><span class="sxs-lookup"><span data-stu-id="b941c-121">Element</span></span>|<span data-ttu-id="b941c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b941c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b941c-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b941c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b941c-124">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b941c-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b941c-125">Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.</span><span class="sxs-lookup"><span data-stu-id="b941c-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b941c-126">Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="b941c-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b941c-127">Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b941c-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b941c-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b941c-128">Remarks</span></span>  
 <span data-ttu-id="b941c-129">Das `<remove>` -Element entfernt einen angegebenen Listener aus `Listeners` der-Auflistung für eine Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="b941c-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b941c-130">Sie können ein Element aus der `Listeners` -Auflistung für eine Ablauf Verfolgungs Quelle Programm gesteuert entfernen, indem Sie die <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> -Methode für <xref:System.Diagnostics.TraceSource> die-Eigenschaft der-Instanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b941c-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="b941c-131">Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b941c-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b941c-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b941c-132">Example</span></span>  
 <span data-ttu-id="b941c-133">Im folgenden Beispiel wird gezeigt, wie das `<remove>` -Element verwendet wird `<add>` , bevor das-Element verwendet wird, um der-Auflistung `TraceSourceApp`für die Ablauf Verfolgungs Quelle den Listener `console` `Listeners` hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b941c-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="b941c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b941c-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b941c-135">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b941c-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b941c-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="b941c-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="b941c-137">Trace Listeners (Ablaufverfolgungslistener)</span><span class="sxs-lookup"><span data-stu-id="b941c-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
