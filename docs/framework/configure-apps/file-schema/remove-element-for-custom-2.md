---
title: <remove> Element für NameValueSectionHandler und DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 062aa3921d29cffd33db2d96096ef25c2b819030
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300701"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="05f28-102">\<Entfernen Sie >-Element für NameValueSectionHandler und DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="05f28-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="05f28-103">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="05f28-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="05f28-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="05f28-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="05f28-105">&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="05f28-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="05f28-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="05f28-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="05f28-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="05f28-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="05f28-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="05f28-108">Attribute</span></span>

|           | <span data-ttu-id="05f28-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05f28-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="05f28-110">**key**</span><span class="sxs-lookup"><span data-stu-id="05f28-110">**key**</span></span>   | <span data-ttu-id="05f28-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="05f28-111">Required attribute.</span></span><br><br><span data-ttu-id="05f28-112">Gibt den Namen der Einstellung, um Sie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="05f28-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="05f28-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="05f28-113">Parent element</span></span>

| <span data-ttu-id="05f28-114">Element</span><span class="sxs-lookup"><span data-stu-id="05f28-114">Element</span></span> | <span data-ttu-id="05f28-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05f28-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="05f28-116"> *\*\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="05f28-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="05f28-117">Definiert die Einstellungen für die benutzerdefinierten Konfigurationsabschnitte, mit denen die <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> Klassen.</span><span class="sxs-lookup"><span data-stu-id="05f28-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="05f28-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05f28-118">Child elements</span></span>

<span data-ttu-id="05f28-119">None</span><span class="sxs-lookup"><span data-stu-id="05f28-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="05f28-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05f28-120">Remarks</span></span>

<span data-ttu-id="05f28-121">Sie können die  **\<entfernen >** Elements, das Einstellungen entfernt, von der Anwendung, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05f28-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="05f28-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05f28-122">Example</span></span>

<span data-ttu-id="05f28-123">Das folgende Beispiel zeigt, wie Sie mit der  **\<entfernen >** Element in einer Anwendungskonfigurationsdatei, entfernen Sie die Einstellungen, die zuvor in der Computerkonfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="05f28-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="05f28-124">Der folgende Konfigurationscode Datei Computer deklariert Abschnitt  **\<MySection >** und fügt zwei Einstellungen `key1` und `key2`, damit:</span><span class="sxs-lookup"><span data-stu-id="05f28-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="05f28-125">Der folgende Code für eine Anwendungskonfigurationsdatei entfernt die `key2` aus  **\<MySection >** :</span><span class="sxs-lookup"><span data-stu-id="05f28-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="05f28-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="05f28-126">Configuration file</span></span>

<span data-ttu-id="05f28-127">Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden ( *"Machine.config"* ), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.</span><span class="sxs-lookup"><span data-stu-id="05f28-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f28-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05f28-128">See also</span></span>

- [<span data-ttu-id="05f28-129">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="05f28-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
