---
title: <system.codedom>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 19f37095bd01b76fda8b1e29423c413dbdb06a65
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168914"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="d6c91-102">\<System. CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="d6c91-102">\<system.codedom> Element</span></span>
<span data-ttu-id="d6c91-103">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="d6c91-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="d6c91-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d6c91-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d6c91-105">&nbsp;&nbsp; **\<System. CodeDom->**</span><span class="sxs-lookup"><span data-stu-id="d6c91-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c91-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6c91-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6c91-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d6c91-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d6c91-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6c91-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6c91-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d6c91-109">Attributes</span></span>  
 <span data-ttu-id="d6c91-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d6c91-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6c91-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6c91-111">Child Elements</span></span>  
  
|<span data-ttu-id="d6c91-112">Element</span><span class="sxs-lookup"><span data-stu-id="d6c91-112">Element</span></span>|<span data-ttu-id="d6c91-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6c91-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c91-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="d6c91-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="d6c91-115">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="d6c91-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6c91-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6c91-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d6c91-117">Element</span><span class="sxs-lookup"><span data-stu-id="d6c91-117">Element</span></span>|<span data-ttu-id="d6c91-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6c91-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c91-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6c91-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="d6c91-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d6c91-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6c91-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6c91-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="d6c91-122">.NET Framework Version 2,0</span><span class="sxs-lookup"><span data-stu-id="d6c91-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="d6c91-123"><xref:Microsoft.CSharp.CSharpCodeProvider> [ Das\<System. CodeDom >](system-codedom-element.md) -Element enthält zusätzlich zu den Standard Anbietern, die mit dem .NET Framework installiert werden, Compilerkonfigurationseinstellungen für Sprachanbieter, die auf einem Computer installiert sind, wie z. b. und. <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="d6c91-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="d6c91-124">[ \<](compiler-element.md) [ Die\<Compiler >](compilers-element.md) -Elements enthalten keine oder mehrere Compiler>-Elemente.</span><span class="sxs-lookup"><span data-stu-id="d6c91-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="d6c91-125">[ Jedes\<Compiler >](compiler-element.md) -Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="d6c91-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="d6c91-126">Entwickler und Compileranbieter können der Computer Konfigurationsdatei (Machine. config) für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung Konfigurationseinstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6c91-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="d6c91-127">Verwenden Sie <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> die-Methode, um die Standard Sprachanbieter und Sprachanbieter, die von den Compilerkonfigurationseinstellungen eines Computers identifiziert werden, Programm gesteuert aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="d6c91-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6c91-128">In den .NET Framework Versionen 1,0 und 1,1 werden die von der .NET Framework bereitgestellten Standard Sprachanbieter im [ \<Compiler >](compilers-element.md) -Element identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d6c91-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="d6c91-129">In der .NET Framework Version 2,0 werden die Standard Sprachanbieter nicht im [ \<Compiler >](compilers-element.md) Element identifiziert, können aber mithilfe der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c91-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="d6c91-130">.NET Framework Versionen 1,0 und 1,1</span><span class="sxs-lookup"><span data-stu-id="d6c91-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="d6c91-131">[ Das\<System. CodeDom->](system-codedom-element.md) -Element enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="d6c91-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="d6c91-132">[ \<](compiler-element.md) [ Die\<Compiler >](compilers-element.md) -Elements enthalten keine oder mehrere Compiler>-Elemente.</span><span class="sxs-lookup"><span data-stu-id="d6c91-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="d6c91-133">[ Jedes\<Compiler >](compiler-element.md) -Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="d6c91-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="d6c91-134">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d6c91-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="d6c91-135">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6c91-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="d6c91-136">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="d6c91-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d6c91-137">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="d6c91-137">Configuration File</span></span>  
 <span data-ttu-id="d6c91-138">Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c91-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6c91-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6c91-139">Example</span></span>  
 <span data-ttu-id="d6c91-140">Das folgende Beispiel veranschaulicht eine typische Compilerkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d6c91-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6c91-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6c91-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="d6c91-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="d6c91-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d6c91-143">Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d6c91-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6c91-144">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="d6c91-144">\<compiler> Element</span></span>](compiler-element.md)
