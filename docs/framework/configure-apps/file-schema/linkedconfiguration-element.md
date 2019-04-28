---
title: <linkedConfiguration>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 909ee7cbb7cd31cf213f305b23237cb69e295882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674648"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="25802-102">\<LinkedConfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="25802-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="25802-103">Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="25802-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="25802-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="25802-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="25802-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="25802-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="25802-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="25802-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="25802-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="25802-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="25802-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="25802-108">Attribute</span></span>

|           | <span data-ttu-id="25802-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25802-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="25802-110">**href**</span><span class="sxs-lookup"><span data-stu-id="25802-110">**href**</span></span>  | <span data-ttu-id="25802-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="25802-111">Required attribute.</span></span><br><br><span data-ttu-id="25802-112">Die URL der Konfigurationsdatei eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="25802-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="25802-113">Die einzige unterstützte Format für die **Href** Attribut `file://`.</span><span class="sxs-lookup"><span data-stu-id="25802-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="25802-114">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25802-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="25802-115">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="25802-115">Parent element</span></span>

|     | <span data-ttu-id="25802-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25802-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="25802-117">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="25802-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="25802-118">Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="25802-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="25802-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25802-119">Child elements</span></span>

<span data-ttu-id="25802-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="25802-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="25802-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25802-121">Remarks</span></span>

<span data-ttu-id="25802-122">Die  **\<LinkedConfiguration >** Element vereinfacht die Wartung für Komponentenassemblys.</span><span class="sxs-lookup"><span data-stu-id="25802-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="25802-123">Wenn eine oder mehrere Anwendungen eine Assembly zu, die über eine Konfigurationsdatei, die sich in einem bekannten Speicherort befinden verwenden, können die Konfigurationsdateien der Anwendungen, die die Assembly der  **\<LinkedConfiguration >** Element, das die Konfigurationsdatei der Assembly, anstatt direkt darunter von Konfigurationsinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="25802-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="25802-124">Wenn die Komponentenassembly gewartet wird, stellt das Aktualisieren der allgemeinen Konfigurationsdatei aktualisierte Konfigurationsinformationen für alle Anwendungen, die die Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25802-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="25802-125">Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25802-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="25802-126">Die folgenden Regeln bestimmen die Verwendung von verknüpfte Konfigurationsdateien:</span><span class="sxs-lookup"><span data-stu-id="25802-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="25802-127">Die Einstellungen in Konfigurationsdateien enthalten nur Auswirkungen auf das Ladeprogramm Bindungsrichtlinie und werden nur vom Ladeprogramm verwendet.</span><span class="sxs-lookup"><span data-stu-id="25802-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="25802-128">Die enthaltenen Konfigurationsdateien haben Einstellungen als die Bindung von Richtlinien, aber diese Einstellungen haben keinerlei Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="25802-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="25802-129">Die einzige unterstützte Format für die `href` Attribut `file://`.</span><span class="sxs-lookup"><span data-stu-id="25802-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="25802-130">Lokale Dateien und UNC-Dateien werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25802-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="25802-131">Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="25802-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="25802-132">Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei, vergleichbar mit dem Verhalten von bilden die `#include` in C/C++-Direktive.</span><span class="sxs-lookup"><span data-stu-id="25802-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="25802-133">Die  **\<LinkedConfiguration >** Element ist nur in Anwendungskonfigurationsdateien zulässig; es wird ignoriert, *"Machine.config"*.</span><span class="sxs-lookup"><span data-stu-id="25802-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="25802-134">Zirkelverweise werden erkannt und beendet.</span><span class="sxs-lookup"><span data-stu-id="25802-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="25802-135">D.h., wenn die  **\<LinkedConfiguration >** Elemente aus einer Reihe von Konfigurationsdateien bilden eine Schleife, die Schleife erkannt und gestoppt wird.</span><span class="sxs-lookup"><span data-stu-id="25802-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="25802-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25802-136">Example</span></span>

<span data-ttu-id="25802-137">Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei aus der lokalen Festplatte enthalten:</span><span class="sxs-lookup"><span data-stu-id="25802-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="25802-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25802-138">See also</span></span>

- [<span data-ttu-id="25802-139">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="25802-139">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="25802-140">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="25802-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
