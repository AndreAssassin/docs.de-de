---
title: <filter> -Element für <add> für <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 2bef729f179b41509d3c0381b26e38e364dbf86b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673718"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="e7f5e-102">\<Filter >-Element für \<hinzufügen > für \<SharedListeners ></span><span class="sxs-lookup"><span data-stu-id="e7f5e-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="e7f5e-103">Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="e7f5e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7f5e-104">\<configuration></span></span>  
<span data-ttu-id="e7f5e-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="e7f5e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e7f5e-106">\<SharedListeners >-Element</span><span class="sxs-lookup"><span data-stu-id="e7f5e-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="e7f5e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e7f5e-107">\<add></span></span>  
<span data-ttu-id="e7f5e-108">\<filter></span><span class="sxs-lookup"><span data-stu-id="e7f5e-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f5e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7f5e-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f5e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f5e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f5e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f5e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7f5e-112">Attributes</span></span>  
  
|<span data-ttu-id="e7f5e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e7f5e-113">Attribute</span></span>|<span data-ttu-id="e7f5e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7f5e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7f5e-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e7f5e-115">**type**</span></span>|<span data-ttu-id="e7f5e-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e7f5e-117">Gibt den Typ des Filters.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-117">Specifies the type of the filter.</span></span> <span data-ttu-id="e7f5e-118">Können Sie nur den vollständigen Namen des Typs (im Format der <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft), oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen (im Format der <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="e7f5e-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="e7f5e-119">Informationen zum Erstellen eines vollständigen Typnamen, finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5e-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="e7f5e-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="e7f5e-120">**initializeData**</span></span>|<span data-ttu-id="e7f5e-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e7f5e-122">Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f5e-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f5e-123">Child Elements</span></span>  
 <span data-ttu-id="e7f5e-124">Keine</span><span class="sxs-lookup"><span data-stu-id="e7f5e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f5e-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f5e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f5e-126">Element</span><span class="sxs-lookup"><span data-stu-id="e7f5e-126">Element</span></span>|<span data-ttu-id="e7f5e-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7f5e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e7f5e-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e7f5e-129">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="e7f5e-130">Eine Auflistung der Listener, die jedes Quell- oder Ablaufverfolgungselement verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="e7f5e-131">Fügt einen Listener, damit die **SharedListeners** Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f5e-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7f5e-132">Remarks</span></span>  
 <span data-ttu-id="e7f5e-133">Wenn ein Listener in definiert ist ein `<add>` Element der `<sharedListeners>` Element der Filter für diesen Listener definiert werden eine `<filter>` -Element, das ein untergeordnetes Element des der `<add>` Element.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="e7f5e-134">Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f5e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7f5e-135">Example</span></span>  
 <span data-ttu-id="e7f5e-136">Das folgende Beispiel zeigt, wie Sie mit der `<filter>` Elemente einen Filter für den Ablaufverfolgungslistener `console` in die `sharedListeners` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e7f5e-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f5e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7f5e-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="e7f5e-138">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e7f5e-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
