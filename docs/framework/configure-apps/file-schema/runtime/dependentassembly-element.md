---
title: <dependentAssembly>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac83a0b27a965721dabe1bdf2e05afbdc9b9c961
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704777"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="b205b-102">\<DependentAssembly >-Element</span><span class="sxs-lookup"><span data-stu-id="b205b-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="b205b-103">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="b205b-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="b205b-104">Verwenden Sie eine `dependentAssembly` -Element für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="b205b-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="b205b-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b205b-105">\<configuration></span></span>  
<span data-ttu-id="b205b-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b205b-106">\<runtime></span></span>  
<span data-ttu-id="b205b-107">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="b205b-107">\<assemblyBinding></span></span>  
<span data-ttu-id="b205b-108">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="b205b-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b205b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b205b-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b205b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b205b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b205b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b205b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b205b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b205b-112">Attributes</span></span>  
 <span data-ttu-id="b205b-113">Keine</span><span class="sxs-lookup"><span data-stu-id="b205b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b205b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b205b-114">Child Elements</span></span>  
  
|<span data-ttu-id="b205b-115">Element</span><span class="sxs-lookup"><span data-stu-id="b205b-115">Element</span></span>|<span data-ttu-id="b205b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b205b-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="b205b-117">Enthält identifizierende Informationen für die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="b205b-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="b205b-118">Dieses Element enthalten sein muss, in den einzelnen `dependentAssembly` Element.</span><span class="sxs-lookup"><span data-stu-id="b205b-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="b205b-119">Gibt an, in dem die Runtime eine freigegebene Assembly finden kann, wenn es nicht auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b205b-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="b205b-120">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="b205b-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="b205b-121">Gibt an, ob für diese Assembly die Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="b205b-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b205b-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b205b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b205b-123">Element</span><span class="sxs-lookup"><span data-stu-id="b205b-123">Element</span></span>|<span data-ttu-id="b205b-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b205b-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="b205b-125">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b205b-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="b205b-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b205b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b205b-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b205b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b205b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b205b-128">Example</span></span>  
 <span data-ttu-id="b205b-129">Das folgende Beispiel zeigt, wie Sie die Assemblyinformationen für zwei Assemblys zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="b205b-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b205b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b205b-130">See also</span></span>

- [<span data-ttu-id="b205b-131">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b205b-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b205b-132">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b205b-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b205b-133">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="b205b-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
