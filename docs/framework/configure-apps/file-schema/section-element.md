---
title: <section> Element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 64556054df2689ff758f52c7e98556997a3e9d3d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301177"
---
# <a name="section-element"></a><span data-ttu-id="0119d-102">\<Abschnitt >-Element</span><span class="sxs-lookup"><span data-stu-id="0119d-102">\<section> element</span></span>

<span data-ttu-id="0119d-103">Enthält die Deklaration einer Konfigurations-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0119d-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="0119d-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0119d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0119d-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0119d-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0119d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Abschnitt >**</span><span class="sxs-lookup"><span data-stu-id="0119d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="0119d-107">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0119d-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0119d-108">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0119d-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0119d-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup>** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="0119d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="0119d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="0119d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0119d-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="0119d-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="0119d-112">Erforderliche Attribute</span><span class="sxs-lookup"><span data-stu-id="0119d-112">Required attributes</span></span>

|           | <span data-ttu-id="0119d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0119d-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0119d-114">**name**</span><span class="sxs-lookup"><span data-stu-id="0119d-114">**name**</span></span>  | <span data-ttu-id="0119d-115">Gibt den Namen des Konfigurationsabschnitts.</span><span class="sxs-lookup"><span data-stu-id="0119d-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="0119d-116">**Typ**</span><span class="sxs-lookup"><span data-stu-id="0119d-116">**type**</span></span>  | <span data-ttu-id="0119d-117">Gibt den Namen der Konfiguration im Abschnitt Handler-Klasse, die im Abschnitt aus der Konfigurationsdatei liest.</span><span class="sxs-lookup"><span data-stu-id="0119d-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="0119d-118">Der Typwert muss es sich um die Syntax "Fully-qualified-section-handler-class-name, Simple-Assembly-Name".</span><span class="sxs-lookup"><span data-stu-id="0119d-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="0119d-119">Der einfachen Assemblynamen ist der Stamm-Dateiname ohne die *DLL* Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="0119d-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="0119d-120">Optionale Attribute</span><span class="sxs-lookup"><span data-stu-id="0119d-120">Optional attributes</span></span>

<span data-ttu-id="0119d-121">Die folgenden Attribute gelten nur für ASP.NET-Anwendungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0119d-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="0119d-122">Das Konfigurationssystem ignoriert diese Attribute für andere Anwendungstypen.</span><span class="sxs-lookup"><span data-stu-id="0119d-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="0119d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0119d-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="0119d-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="0119d-124">**allowDefinition**</span></span> | <span data-ttu-id="0119d-125">Gibt die Konfigurationsdatei an, die in Abschnitt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0119d-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="0119d-126">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="0119d-126">Use one of the following values:</span></span><br><br><span data-ttu-id="0119d-127">**Überall**</span><span class="sxs-lookup"><span data-stu-id="0119d-127">**Everywhere**</span></span><br><span data-ttu-id="0119d-128">Können den Abschnitt in den Konfigurationsdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0119d-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="0119d-129">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0119d-129">This is the default.</span></span><br><span data-ttu-id="0119d-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="0119d-130">**MachineOnly**</span></span><br><span data-ttu-id="0119d-131">Der Abschnitt kann nur in der Computerkonfigurationsdatei verwendet werden ( *"Machine.config"* ).</span><span class="sxs-lookup"><span data-stu-id="0119d-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="0119d-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="0119d-132">**MachineToApplication**</span></span><br><span data-ttu-id="0119d-133">Können den Abschnitt in der Konfigurationsdatei des Computers oder der Konfigurationsdatei der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0119d-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="0119d-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="0119d-134">**allowLocation**</span></span>   | <span data-ttu-id="0119d-135">Bestimmt, ob im Abschnitt kann, in verwendet werden der  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="0119d-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="0119d-136">Verwenden Sie einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="0119d-136">Use one of the following values:</span></span><br><br><span data-ttu-id="0119d-137">**true**</span><span class="sxs-lookup"><span data-stu-id="0119d-137">**true**</span></span><br><span data-ttu-id="0119d-138">Der Abschnitt kann verwendet werden die  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="0119d-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="0119d-139">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0119d-139">This is the default.</span></span><br><span data-ttu-id="0119d-140">**false**</span><span class="sxs-lookup"><span data-stu-id="0119d-140">**false**</span></span><br><span data-ttu-id="0119d-141">Im Abschnitt zu verwendenden lässt nicht zu den  **\<Speicherort >** Element.</span><span class="sxs-lookup"><span data-stu-id="0119d-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="0119d-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0119d-142">Parent elements</span></span>

|     | <span data-ttu-id="0119d-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0119d-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0119d-144"> *\*\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="0119d-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="0119d-145">Enthält die Konfiguration im Abschnitt und Namespacedeklarationen.</span><span class="sxs-lookup"><span data-stu-id="0119d-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="0119d-146"> *\*\<sectionGroup>** Element</span><span class="sxs-lookup"><span data-stu-id="0119d-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="0119d-147">Definiert einen Namespace für Konfigurationsabschnitte.</span><span class="sxs-lookup"><span data-stu-id="0119d-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="0119d-148">Ein  **\<Abschnitt >** Element ist ein untergeordnetes Element des entweder  **\<ConfigSections >** oder  **\<SectionGroup >** aber nicht beide.</span><span class="sxs-lookup"><span data-stu-id="0119d-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="0119d-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0119d-149">Child elements</span></span>

<span data-ttu-id="0119d-150">None</span><span class="sxs-lookup"><span data-stu-id="0119d-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0119d-151">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0119d-151">Remarks</span></span>

<span data-ttu-id="0119d-152">Deklarieren im Wesentlichen einen Konfigurationsabschnitt definiert ein neues Element für die Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="0119d-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="0119d-153">Das neue Element enthält Einstellungen, die eine Konfiguration Handler im Abschnitt (d. h. eine Klasse, implementiert die <xref:System.Configuration.IConfigurationSectionHandler> Schnittstelle) liest.</span><span class="sxs-lookup"><span data-stu-id="0119d-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="0119d-154">Die Attribute und untergeordneten Elemente eines Abschnitts, die Sie definieren, hängt von der Abschnittshandler, die, den Sie verwenden, um Ihre Einstellungen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="0119d-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="0119d-155">Deklarieren einen Konfigurationsabschnittshandler in der *"Machine.config"* Datei können Sie Abschnitt "Konfiguration" in den Konfigurationsdateien der Anwendung auf diesem Computer verwenden, es sei denn, die **AllowDefinition**Attribut angibt.</span><span class="sxs-lookup"><span data-stu-id="0119d-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="0119d-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0119d-156">Example</span></span>

<span data-ttu-id="0119d-157">Das folgende Beispiel zeigt, wie Sie definieren einen Konfigurationsabschnitt aus, und definieren Sie Einstellungen für diesen Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="0119d-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0119d-158">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0119d-158">Configuration file</span></span>

<span data-ttu-id="0119d-159">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="0119d-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0119d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0119d-160">See also</span></span>

- [<span data-ttu-id="0119d-161">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0119d-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
