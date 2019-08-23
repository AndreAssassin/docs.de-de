---
title: <add>-Element für <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 8fcd5cbe63a323a7509f5ff8c615364295c244d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920549"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="911ec-102">\<Fügen Sie > Element \<für Switches hinzu ></span><span class="sxs-lookup"><span data-stu-id="911ec-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="911ec-103">Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="911ec-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="911ec-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="911ec-104">\<configuration></span></span>  
<span data-ttu-id="911ec-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="911ec-105">\<system.diagnostics></span></span>  
<span data-ttu-id="911ec-106">\<Schalter ></span><span class="sxs-lookup"><span data-stu-id="911ec-106">\<switches></span></span>  
<span data-ttu-id="911ec-107">\<add></span><span class="sxs-lookup"><span data-stu-id="911ec-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911ec-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="911ec-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="911ec-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="911ec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="911ec-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="911ec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="911ec-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="911ec-111">Attributes</span></span>  
  
|<span data-ttu-id="911ec-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="911ec-112">Attribute</span></span>|<span data-ttu-id="911ec-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911ec-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="911ec-114">**name**</span><span class="sxs-lookup"><span data-stu-id="911ec-114">**name**</span></span>|<span data-ttu-id="911ec-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="911ec-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="911ec-116">Gibt den Namen des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="911ec-116">Specifies the name of the switch.</span></span> <span data-ttu-id="911ec-117">Der Wert dieses Attributs entspricht dem *DisplayName* -Parameter, der an den Switch-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="911ec-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="911ec-118">**value**</span><span class="sxs-lookup"><span data-stu-id="911ec-118">**value**</span></span>|<span data-ttu-id="911ec-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="911ec-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="911ec-120">Gibt die Ebene des Schalters an.</span><span class="sxs-lookup"><span data-stu-id="911ec-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="911ec-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="911ec-121">Child Elements</span></span>  
 <span data-ttu-id="911ec-122">Keine</span><span class="sxs-lookup"><span data-stu-id="911ec-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="911ec-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="911ec-123">Parent Elements</span></span>  
  
|<span data-ttu-id="911ec-124">Element</span><span class="sxs-lookup"><span data-stu-id="911ec-124">Element</span></span>|<span data-ttu-id="911ec-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911ec-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="911ec-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="911ec-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="911ec-127">Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="911ec-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="911ec-128">Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="911ec-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="911ec-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="911ec-129">Remarks</span></span>  
 <span data-ttu-id="911ec-130">Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="911ec-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="911ec-131">Wenn der Schalter ein <xref:System.Diagnostics.BooleanSwitch>ist, können Sie ihn aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="911ec-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="911ec-132">Wenn der Schalter ein <xref:System.Diagnostics.TraceSwitch>ist, können Sie ihm verschiedene Ebenen zuweisen, um die Typen der Ablauf Verfolgungs-oder Debugmeldungen anzugeben, die die Anwendung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="911ec-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="911ec-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="911ec-133">Example</span></span>  
 <span data-ttu-id="911ec-134">Im folgenden Beispiel wird gezeigt, wie das  **\<Add >** -Element verwendet wird `General` , um den Ablauf <xref:System.Diagnostics.TraceLevel> Verfolgungs Schalter auf die Ebene `Data` festzulegen und den booleschen Ablauf Verfolgungs Schalter zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="911ec-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="911ec-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="911ec-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="911ec-136">Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="911ec-136">Trace and Debug Settings Schema</span></span>](index.md)
