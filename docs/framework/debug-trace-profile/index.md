---
title: Debuggen, Ablaufverfolgung und Profilerstellung
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43927be83b8b2a9163656f8d6d54c2cf83a23e28
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052651"
---
# <a name="debugging-tracing-and-profiling"></a><span data-ttu-id="4c02a-102">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="4c02a-102">Debugging, Tracing, and Profiling</span></span>
<span data-ttu-id="4c02a-103">Um eine .NET Framework-Anwendung debuggen zu können, müssen der Compiler und die Laufzeitumgebung so konfiguriert sein, dass ein Debugger an die Anwendung angefügt werden und der Debugger, wenn möglich, sowohl Symbole als auch Zeilenzuordnungen für die Anwendung und deren entsprechende Microsoft Intermediate Language (MSIL) erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4c02a-103">To debug a .NET Framework application, the compiler and runtime environment must be configured to enable a debugger to attach to the application and to produce both symbols and line maps, if possible, for the application and its corresponding Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="4c02a-104">Nach dem Debuggen einer verwalteten Anwendung kann ein Profil für sie erstellt werden, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4c02a-104">After a managed application has been debugged, it can be profiled to boost performance.</span></span> <span data-ttu-id="4c02a-105">Bei einer Profilerstellung werden die Quellcodezeilen bewertet und beschrieben, die den am häufigsten ausgeführten Code generieren, und wird ermittelt, wie lange es dauert, diese auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4c02a-105">Profiling evaluates and describes the lines of source code that generate the most frequently executed code, and how much time it takes to execute them.</span></span>  
  
 <span data-ttu-id="4c02a-106">.NET Framework-Anwendungen lassen sich problemlos mit Visual Studio debuggen, das viele der Konfigurationsdetails verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4c02a-106">.NET Framework applications are easily debugged by using Visual Studio, which handles many of the configuration details.</span></span> <span data-ttu-id="4c02a-107">Wenn Visual Studio nicht installiert ist, können Sie die Leistung von .NET Framework-Anwendungen mithilfe der Debuggingklassen im <xref:System.Diagnostics>-Namespace von .NET Framework prüfen und verbessern.</span><span class="sxs-lookup"><span data-stu-id="4c02a-107">If Visual Studio is not installed, you can examine and improve the performance of .NET Framework applications by using the debugging classes in the .NET Framework <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="4c02a-108">Dieser Namespace enthält die Klassen <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> und <xref:System.Diagnostics.TraceSource> zum Nachverfolgen des Ausführungsablaufs und die Klassen <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> und <xref:System.Diagnostics.PerformanceCounter> für die Codeprofilierung.</span><span class="sxs-lookup"><span data-stu-id="4c02a-108">This namespace includes the <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug>, and <xref:System.Diagnostics.TraceSource> classes for tracing execution flow, and the <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog>, and <xref:System.Diagnostics.PerformanceCounter> classes for profiling code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c02a-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4c02a-109">In This Section</span></span>  
 [<span data-ttu-id="4c02a-110">Aktivieren von JIT-attach Debugging</span><span class="sxs-lookup"><span data-stu-id="4c02a-110">Enabling JIT-Attach Debugging</span></span>](enabling-jit-attach-debugging.md)  
 <span data-ttu-id="4c02a-111">Zeigt, wie die Registrierung zu konfigurieren ist, um eine Debug-Engine an eine .NET Framework-Anwendung anzufügen (JIT-attach Debugging).</span><span class="sxs-lookup"><span data-stu-id="4c02a-111">Shows how to configure the registry to JIT-attach a debug engine to a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="4c02a-112">Erleichtern des Debuggens für ein Abbild</span><span class="sxs-lookup"><span data-stu-id="4c02a-112">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)  
 <span data-ttu-id="4c02a-113">Zeigt, wie die JIT-Verfolgung aktiviert und die Optimierung deaktiviert wird, damit sich eine Assembly einfacher debuggen lässt.</span><span class="sxs-lookup"><span data-stu-id="4c02a-113">Shows how to turn JIT tracking on and optimization off to make an assembly easier to debug.</span></span>  
  
 [<span data-ttu-id="4c02a-114">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4c02a-114">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="4c02a-115">Beschreibt, wie die Ausführung einer Anwendung überwacht und wie diese instrumentiert werden kann, um anzuzeigen, wie gut die Anwendung ausgeführt wird oder ob etwaige Fehler aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="4c02a-115">Describes how to monitor the execution of your application while it is running, and how to instrument it to display how well it is performing or whether something has gone wrong.</span></span>  
  
 [<span data-ttu-id="4c02a-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="4c02a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)  
 <span data-ttu-id="4c02a-117">Beschreibt MDAs (Managed Debugging Assistants, Assistenten für verwaltetes Debuggen), die Hilfsmittel für das Debuggen sind, die mit der CLR (Common Language Runtime) zusammenarbeiten, um Informationen über den Laufzeitzustand bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c02a-117">Describes managed debugging assistants (MDAs), which are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span>  
  
 [<span data-ttu-id="4c02a-118">Verbessern des Debuggens mit den Debuggeranzeigeattributen</span><span class="sxs-lookup"><span data-stu-id="4c02a-118">Enhancing Debugging with the Debugger Display Attributes</span></span>](enhancing-debugging-with-the-debugger-display-attributes.md)  
 <span data-ttu-id="4c02a-119">Beschreibt, wie der Entwickler eines Typs angeben kann, wie der Typ aussieht, wenn er in einem Debugger angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c02a-119">Describes how the developer of a type can specify what that type will look like when it is displayed in a debugger.</span></span>  
  
 [<span data-ttu-id="4c02a-120">Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="4c02a-120">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="4c02a-121">Beschreibt die Leistungsindikatoren, die Sie zum Überwachen der Leistung einer Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4c02a-121">Describes the counters that you can use to track the performance of an application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4c02a-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4c02a-122">Related Sections</span></span>  
 [<span data-ttu-id="4c02a-123">ASP.net-oder ASP.net Core-apps in Visual Studio debuggen</span><span class="sxs-lookup"><span data-stu-id="4c02a-123">Debug ASP.NET or ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/debugging-aspnet-and-ajax-applications)  
 <span data-ttu-id="4c02a-124">Enthält Voraussetzungen und Anweisungen für das Debuggen einer ASP.NET-Anwendung während der Entwicklung oder nach der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4c02a-124">Provides prerequisites and instructions for how to debug an ASP.NET application during development or after deployment.</span></span>  
  
 [<span data-ttu-id="4c02a-125">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="4c02a-125">Development Guide</span></span>](../development-guide.md)  
 <span data-ttu-id="4c02a-126">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="4c02a-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
