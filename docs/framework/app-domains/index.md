---
title: Programmieren mit Anwendungsdomänen und Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4f0c2ad1290a7f9cf8d0c43c504a3e0a9628b86
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971927"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="84651-102">Programmieren mit Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="84651-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="84651-103">Hosts wie z.B. Microsoft Internet Explorer, ASP.NET und Windows-Shell laden die Common Language Runtime in einen Prozess, erstellen eine [Anwendungsdomäne](../../../docs/framework/app-domains/application-domains.md) in diesem Prozess und laden dann Benutzercode in diese Anwendungsdomäne und führen ihn aus, wenn eine .NET Framework-Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84651-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="84651-104">In den meisten Fällen müssen Sie sich nicht darum kümmern, Anwendungsdomänen zu erstellen und Assemblys hinein zu laden, da der Laufzeithost diese Aufgaben ausführt.</span><span class="sxs-lookup"><span data-stu-id="84651-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="84651-105">Wenn Sie jedoch eine Anwendung erstellen, die die Common Language Runtime hostet, Tools oder Code erstellen, den Sie programmgesteuert entladen möchten, oder austauschbare Komponenten erstellen, die spontan entladen und neu geladen werden können, erstellen Sie Ihre eigenen Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="84651-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="84651-106">Auch wenn Sie keinen Laufzeithost erstellen, können Sie diesem Abschnitt wichtige Informationen entnehmen zum Arbeiten mit Anwendungsdomänen und Assemblys, die in diese Anwendungsdomänen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="84651-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84651-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84651-107">In This Section</span></span>  
 [<span data-ttu-id="84651-108">Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="84651-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="84651-109">Enthält Links zu allen Gewusst-wie-Themen in der Begriffsdokumentation zum Programmieren mit Anwendungsdomänen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="84651-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="84651-110">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="84651-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="84651-111">Stellt Beispiele zum Erstellen, Konfigurieren und Verwenden von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="84651-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="84651-112">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="84651-112">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
 <span data-ttu-id="84651-113">Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.</span><span class="sxs-lookup"><span data-stu-id="84651-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="84651-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="84651-114">Related Sections</span></span>  
 [<span data-ttu-id="84651-115">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="84651-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="84651-116">Beschreibt das Erstellen dynamischer Assemblys.</span><span class="sxs-lookup"><span data-stu-id="84651-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="84651-117">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="84651-117">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
 <span data-ttu-id="84651-118">Bietet eine konzeptionelle Übersicht über Assemblys.</span><span class="sxs-lookup"><span data-stu-id="84651-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="84651-119">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="84651-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="84651-120">Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="84651-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="84651-121">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="84651-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="84651-122">Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="84651-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
