---
title: <remove>-Element für "NameValueSectionHandler" und "diktarysectionhandler"
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc1519a794e24e04074dd2a674ecc2c0f3666521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118562"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ead44-102">\<> Element für NameValueSectionHandler und "diktarysectionhandler" entfernen</span><span class="sxs-lookup"><span data-stu-id="ead44-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ead44-103">Entfernt eine zuvor definierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ead44-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="ead44-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ead44-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="ead44-105">&nbsp;&nbsp;[ **\<sectionName->** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="ead44-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="ead44-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="ead44-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ead44-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ead44-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="ead44-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="ead44-108">Attribute</span></span>

|           | <span data-ttu-id="ead44-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ead44-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ead44-110">**key**</span><span class="sxs-lookup"><span data-stu-id="ead44-110">**key**</span></span>   | <span data-ttu-id="ead44-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ead44-111">Required attribute.</span></span><br><br><span data-ttu-id="ead44-112">Gibt den Namen der zu entfernenden Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="ead44-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ead44-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="ead44-113">Parent element</span></span>

| <span data-ttu-id="ead44-114">Element</span><span class="sxs-lookup"><span data-stu-id="ead44-114">Element</span></span> | <span data-ttu-id="ead44-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ead44-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="ead44-116"> **\<sectionName >** Gewisses</span><span class="sxs-lookup"><span data-stu-id="ead44-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="ead44-117">Definiert Einstellungen für benutzerdefinierte Konfigurations Abschnitte, in denen die Klassen <xref:System.Configuration.NameValueSectionHandler> und <xref:System.Configuration.DictionarySectionHandler> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ead44-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ead44-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ead44-118">Child elements</span></span>

<span data-ttu-id="ead44-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="ead44-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ead44-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ead44-120">Remarks</span></span>

<span data-ttu-id="ead44-121">Sie können das **\<remove >** -Element verwenden, um Einstellungen aus der Anwendung zu entfernen, die auf einer höheren Ebene in der Hierarchie der Konfigurationsdatei definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ead44-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ead44-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ead44-122">Example</span></span>

<span data-ttu-id="ead44-123">Im folgenden Beispiel wird gezeigt, wie das **\<remove >** -Elements in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computer Konfigurationsdatei definierten Einstellungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ead44-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ead44-124">Der folgende Computer Konfigurationsdatei-Code deklariert den Abschnitt **\<mySection >** und fügt ihm zwei Einstellungen hinzu, `key1` und `key2`:</span><span class="sxs-lookup"><span data-stu-id="ead44-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="ead44-125">Der folgende Anwendungs Konfigurationsdatei-Code entfernt die `key2` Einstellung aus **\<mySection->** :</span><span class="sxs-lookup"><span data-stu-id="ead44-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ead44-126">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ead44-126">Configuration file</span></span>

<span data-ttu-id="ead44-127">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="ead44-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ead44-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ead44-128">See also</span></span>

- [<span data-ttu-id="ead44-129">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ead44-129">Configuration file schema for the .NET Framework</span></span>](index.md)
