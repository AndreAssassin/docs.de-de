---
title: Konfigurationsdateischema für .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: c3b5518b4b86c2e6f47825d552f49579c5ac0a6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921029"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="1a929-102">Konfigurationsdateischema für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a929-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="1a929-103">Konfigurationsdateien sind Standard-XML-Dateien, die Sie verwenden können, um für Ihre Apps Einstellungen zu ändern und Richtlinien festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1a929-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="1a929-104">Das .NET Framework-Konfigurationsschema besteht aus Elementen, die Sie in Konfigurationsdateien verwenden können, um das Verhalten der Apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1a929-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="1a929-105">Das Inhaltsverzeichnis dieses Abschnitts gibt die Schemahierarchie für Startup, Laufzeit, Netzwerk und anderen Arten von Konfigurationseinstellungen wider.</span><span class="sxs-lookup"><span data-stu-id="1a929-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="1a929-106">Informationen über die Typen, das Format und den Speicherort der Konfigurationsdateien finden Sie im Artikel [Configuring Apps (Konfigurieren von Apps)](../index.md).</span><span class="sxs-lookup"><span data-stu-id="1a929-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](../index.md).</span></span> <span data-ttu-id="1a929-107">Machen Sie sich mit XML vertraut, wenn Sie die Konfigurationsdateien direkt bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="1a929-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a929-108">Bei XML-Tags und -Attributen in Konfigurationsdateien muss die Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1a929-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1a929-109">In this section</span></span>

<span data-ttu-id="1a929-110">[ **\<configuration>** -Element](configuration-element.md): Beschreibt das `<configuration>`-Element, das sämtlichen Konfigurationsdateien übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1a929-110">[**\<configuration>** Element](configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="1a929-111">[ **\<assemblyBinding>** -Element](assemblybinding-element-for-configuration.md): Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.</span><span class="sxs-lookup"><span data-stu-id="1a929-111">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="1a929-112">[ **\<linkedConfiguration>** -Element](linkedconfiguration-element.md) Gibt eine einzuschließende Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="1a929-112">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="1a929-113">[Startup Settings Schema (Schema für Starteinstellungen)](./startup/index.md): Beschreibt die Elemente, die angeben, welche Version der Common Language Runtime zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="1a929-113">[Startup Settings Schema](./startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="1a929-114">[Runtime Settings Schema (Schema für Laufzeiteinstellungen)](./runtime/index.md): Beschreibt die Elemente, die die Assemblybindung und das Laufzeitverhalten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a929-114">[Runtime Settings Schema](./runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="1a929-115">[Network Settings Schema (Schema für Netzwerkeinstellungen)](./network/index.md): Beschreibt die Elemente, die angeben, wie Verbindungen zwischen .NET Framework und dem Internet hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-115">[Network Settings Schema](./network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="1a929-116">[Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](./cryptography/index.md): Beschreibt die Elemente, mit denen die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.</span><span class="sxs-lookup"><span data-stu-id="1a929-116">[Cryptography Settings Schema](./cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="1a929-117">[Configuration Sections Schema (Schema für Konfigurationsabschnitte)](configuration-sections-schema.md): Beschreibt die Elemente, mit denen Konfigurationsabschnitte für benutzerdefinierte Einstellungen erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-117">[Configuration Sections Schema](configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="1a929-118">[Trace and Debug Settings Schema (Schema für die Ablaufverfolgungs- und Debugeinstellungen)](./trace-debug/index.md): Beschreibt die Elemente, mit denen Ablaufverfolgungsschalter und -listener angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-118">[Trace and Debug Settings Schema](./trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="1a929-119">[Compiler and Language Provider Settings Schema (Schema für die Compiler- und Sprachanbietereinstellungen)](./compiler/index.md): Beschreibt die Elemente, die die Compilerkonfiguration für verfügbare Sprachanbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="1a929-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="1a929-120">[Application Settings Schema (Schema für die Anwendungseinstellungen)](application-settings-schema.md): Beschreibt die Elemente, die es Windows Forms- oder ASP.NET-Anwendungen ermöglichen, Einstellungen im Gültigkeitsbereich der Anwendung und im Gültigkeitsbereich des Benutzers zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1a929-120">[Application Settings Schema](application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="1a929-121">[App Settings Schema (Schema für die App-Einstellungen)](./appsettings/index.md): Dieses Thema enthält benutzerdefinierte Anwendungseinstellung, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a929-121">[App Settings Schema](./appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="1a929-122">[Web Settings Schema (Schema für die Webeinstellungen)](./web/index.md): Alle Elemente im Webeinstellungsschema, einschließlich des Elements für die Konfiguration von ASP.NET mit einer Hostanwendung wie IIS.</span><span class="sxs-lookup"><span data-stu-id="1a929-122">[Web Settings Schema](./web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="1a929-123">Wird in *Aspnet.config*-Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a929-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="1a929-124">[Windows Forms Configuration Schema (Windows Forms-Konfigurationsschema)](winforms/index.md): Alle Elemente im Konfigurationsabschnitt der Windows Forms-Anwendung, einschließlich Anpassungen, z.B. für die Unterstützung von mehreren Bildschirmen und hohen DPI-Werten.</span><span class="sxs-lookup"><span data-stu-id="1a929-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="1a929-125">[WCF Configuration Schema (WCF-Konfigurationsschema)](./wcf/index.md): Alle Elemente, die es Ihnen ermöglichen, WCF-Dienste und -Clientanwendungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a929-125">[WCF Configuration Schema](./wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="1a929-126">[WCF Directive Syntax (WCF-Anweisungssyntax)](./wcf-directive/index.md): Beschreibt die `@ServiceHost`-Anweisung, die seitenspezifische Attribute definiert, die vom .svc-Compiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-126">[WCF Directive Syntax](./wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="1a929-127">[WIF Configuration Schema (WIF-Konfigurationsschema)](windows-identity-foundation/index.md): Alle Elemente des WIF-Konfigurationsschemas (Windows Identity Foundation).</span><span class="sxs-lookup"><span data-stu-id="1a929-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="1a929-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1a929-128">Related sections</span></span>

<span data-ttu-id="1a929-129">[Remoting Settings Schema (Schema für die Remoteeinstellungen)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)): Beschreibt die Elemente, mit denen Client- und Serveranwendungen konfiguriert werden, die Remotefunktionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="1a929-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="1a929-130">[ASP.NET Settings Schema (Schema für die ASP.NET-Einstellungen)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)): Beschreibt die Elemente, die das Verhalten von ASP.NET-Webanwendungen steuern.</span><span class="sxs-lookup"><span data-stu-id="1a929-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="1a929-131">[Web Services Settings Schema (Schema für die Webdiensteinstellungen)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)): Das Einstellungsschema für Webdienste definiert Konfigurationsdateielemente, die das Verhalten von ASP.NET-Webdiensten und deren Clients steuern.</span><span class="sxs-lookup"><span data-stu-id="1a929-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="1a929-132">[Configuring .NET Framework Apps (Konfigurieren von .NET Framework-Apps)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)): Beschreibt, wie Sicherheit, Assemblybindung und Remotefunktionen in .NET Framework konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a929-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
