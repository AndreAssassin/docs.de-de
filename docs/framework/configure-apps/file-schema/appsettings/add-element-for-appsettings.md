---
title: <add>-Element für <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: f8b426dc0e1e180afbfccce50d3b45774991a572
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301347"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="b3cd9-102">\<Hinzufügen >-Element für \<AppSettings ></span><span class="sxs-lookup"><span data-stu-id="b3cd9-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="b3cd9-103">Fügt eine benutzerdefinierte anwendungseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-103">Adds a custom application setting.</span></span>

<span data-ttu-id="b3cd9-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b3cd9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b3cd9-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b3cd9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="b3cd9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="b3cd9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b3cd9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3cd9-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="b3cd9-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3cd9-108">Attributes</span></span>

|           | <span data-ttu-id="b3cd9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3cd9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b3cd9-110">**key**</span><span class="sxs-lookup"><span data-stu-id="b3cd9-110">**key**</span></span>   | <span data-ttu-id="b3cd9-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-111">Required attribute.</span></span><br><br><span data-ttu-id="b3cd9-112">Gibt den Namen des hinzuzufügenden Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="b3cd9-113">**value**</span><span class="sxs-lookup"><span data-stu-id="b3cd9-113">**value**</span></span> | <span data-ttu-id="b3cd9-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-114">Required attribute.</span></span><br><br><span data-ttu-id="b3cd9-115">Gibt den Wert des hinzuzufügenden Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b3cd9-116">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="b3cd9-116">Parent element</span></span>

|     | <span data-ttu-id="b3cd9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3cd9-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b3cd9-118"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="b3cd9-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="b3cd9-119">Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b3cd9-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b3cd9-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3cd9-120">Child elements</span></span>

<span data-ttu-id="b3cd9-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="b3cd9-121">None</span></span>

## <a name="example"></a><span data-ttu-id="b3cd9-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3cd9-122">Example</span></span>

<span data-ttu-id="b3cd9-123">Das folgende Beispiel zeigt, wie eine benutzerdefinierte Einstellung für den Namen der Anwendung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b3cd9-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="b3cd9-124">Im folgenden Beispiel wird die `<add>` Element, um zwei Einstellungen in einer ASP.NET-Anwendung zu definieren:</span><span class="sxs-lookup"><span data-stu-id="b3cd9-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="b3cd9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3cd9-125">See also</span></span>

- [<span data-ttu-id="b3cd9-126">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3cd9-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
