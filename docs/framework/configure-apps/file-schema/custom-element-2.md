---
title: Benutzerdefiniertes Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8636050b2618d1b2c2da0c08c756b0ed221c7f6f
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300757"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5fac1-102">Benutzerdefiniertes Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="5fac1-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5fac1-103">Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="5fac1-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="5fac1-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span><span class="sxs-lookup"><span data-stu-id="5fac1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span></span>
<span data-ttu-id="5fac1-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="5fac1-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="5fac1-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="5fac1-106">Attributes</span></span>

<span data-ttu-id="5fac1-107">Keiner</span><span class="sxs-lookup"><span data-stu-id="5fac1-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="5fac1-108">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="5fac1-108">Parent element</span></span>

|     | <span data-ttu-id="5fac1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fac1-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5fac1-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5fac1-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="5fac1-111">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5fac1-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5fac1-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5fac1-112">Child elements</span></span>

|     | <span data-ttu-id="5fac1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fac1-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="5fac1-114">[ **\<Hinzufügen >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5fac1-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="5fac1-115">Fügt benutzerdefinierte Anwendungseinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="5fac1-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="5fac1-116">[ **\<Entfernen Sie >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5fac1-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="5fac1-117">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="5fac1-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="5fac1-118">[ **\<Deaktivieren Sie >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) für <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5fac1-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="5fac1-119">Löscht alle zuvor definierte Einstellungen in einem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5fac1-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5fac1-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fac1-120">Remarks</span></span>

<span data-ttu-id="5fac1-121">Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element, das definiert, indem eine  **\<Abschnitt >** -Tag in die  **\<ConfigSections >** Element.</span><span class="sxs-lookup"><span data-stu-id="5fac1-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="5fac1-122">Die folgende Tabelle zeigt, dass der Typ des Objekts die ConfigurationSettings.GetConfig-Methode für jede Konfigurationsabschnittshandler zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="5fac1-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="5fac1-123">Konfigurationsabschnittshandler</span><span class="sxs-lookup"><span data-stu-id="5fac1-123">Configuration section handler</span></span>                        | <span data-ttu-id="5fac1-124">Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="5fac1-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="5fac1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fac1-125">Example</span></span>

<span data-ttu-id="5fac1-126">Das folgende Beispiel zeigt, wie Sie die Abschnitte zu deklarieren, mit denen die <xref:System.Configuration.DictionarySectionHandler> und <xref:System.Configuration.NameValueSectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="5fac1-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="5fac1-127">Das erste benutzerdefinierte Element ist  **\<DictionarySample >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.DictionarySectionHandler> -Klasse in der `System.dll` Assembly.</span><span class="sxs-lookup"><span data-stu-id="5fac1-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="5fac1-128">Das zweite benutzerdefinierte Element ist  **\<MySection >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.NameValueSectionHandler> -Klasse in der `System.dll` Assembly.</span><span class="sxs-lookup"><span data-stu-id="5fac1-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5fac1-129">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="5fac1-129">Configuration file</span></span>

<span data-ttu-id="5fac1-130">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="5fac1-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fac1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fac1-131">See also</span></span>

- [<span data-ttu-id="5fac1-132">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5fac1-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
