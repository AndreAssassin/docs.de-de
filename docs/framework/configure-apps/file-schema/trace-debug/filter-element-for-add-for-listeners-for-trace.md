---
title: <filter> -Element für <add> für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: 5961125e1b8d0d0f5711f8b942b68ba71d61888f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143428"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="22702-102">\<Filter >-Element für \<hinzufügen > für \<Listener > für \<Ablaufverfolgung ></span><span class="sxs-lookup"><span data-stu-id="22702-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="22702-103">Fügt einen Filter zu einem Listener in der `Listeners` Sammlung für eine Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="22702-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="22702-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22702-104">\<configuration></span></span>  
<span data-ttu-id="22702-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="22702-105">\<system.diagnostics></span></span>  
<span data-ttu-id="22702-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="22702-106">\<trace></span></span>  
<span data-ttu-id="22702-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="22702-107">\<listeners></span></span>  
<span data-ttu-id="22702-108">\<add></span><span class="sxs-lookup"><span data-stu-id="22702-108">\<add></span></span>  
<span data-ttu-id="22702-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="22702-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22702-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="22702-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22702-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="22702-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22702-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="22702-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22702-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="22702-113">Attributes</span></span>  
  
|<span data-ttu-id="22702-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="22702-114">Attribute</span></span>|<span data-ttu-id="22702-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22702-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="22702-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="22702-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="22702-117">Gibt den Typ des Filters an, der von erben soll die <xref:System.Diagnostics.TraceFilter> Klasse.</span><span class="sxs-lookup"><span data-stu-id="22702-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="22702-118">Sie können den Namespace-qualifizierten Namen des Typs, der des Typs entspricht <xref:System.Type.FullName%2A> -Eigenschaft, oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen, die entspricht der <xref:System.Type.AssemblyQualifiedName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="22702-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="22702-119">Weitere Informationen zu vollqualifizierten Typnamen, finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="22702-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="22702-120">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="22702-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="22702-121">Die Zeichenfolge, die für die angegebenen Filter-Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="22702-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22702-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22702-122">Child Elements</span></span>  
 <span data-ttu-id="22702-123">Keine</span><span class="sxs-lookup"><span data-stu-id="22702-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22702-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22702-124">Parent Elements</span></span>  
  
|<span data-ttu-id="22702-125">Element</span><span class="sxs-lookup"><span data-stu-id="22702-125">Element</span></span>|<span data-ttu-id="22702-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22702-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22702-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="22702-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="22702-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="22702-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="22702-129">Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="22702-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="22702-130">Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="22702-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="22702-131">Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.</span><span class="sxs-lookup"><span data-stu-id="22702-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="22702-132">Fügt einen Listener zu der `Listeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="22702-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22702-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22702-133">Remarks</span></span>  
 <span data-ttu-id="22702-134">Die `<filter>` Element muss enthalten sein, eine `<add>` -Element für einen Ablaufverfolgungslistener, der den Typ des Listeners, der angibt, die nicht nur der Namen eines Listeners in definiert eine [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="22702-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="22702-135">Wenn der Listener in definiert ist eine [ \<SharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), muss der Filter für diesen Listener in diesem Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="22702-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="22702-136">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22702-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22702-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22702-137">Example</span></span>  
 <span data-ttu-id="22702-138">Das folgende Beispiel zeigt, wie Sie mit der `<filter>` Element um einen Filter hinzuzufügen, mit dem Listener `console` in die `Listeners` -Sammlung für die Ablaufverfolgung, die Angabe der Ebene des Filter-Ereignis als `Error`.</span><span class="sxs-lookup"><span data-stu-id="22702-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22702-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22702-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="22702-140">Schema für Ablaufverfolgungs- und Debugeinstellungen</span><span class="sxs-lookup"><span data-stu-id="22702-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
