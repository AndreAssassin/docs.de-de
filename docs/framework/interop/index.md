---
title: Interoperabilität mit nicht verwaltetem Code
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edec95ea729fdf26e384b6658c241ca307e60851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61643113"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="12bf8-102">Interoperabilität mit nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="12bf8-102">Interoperating with unmanaged code</span></span>

<span data-ttu-id="12bf8-103">.NET Framework stuft die Interaktion mit COM-Komponenten, COM+-Diensten, externen Typbibliotheken und vielen Betriebssystemdiensten herauf.</span><span class="sxs-lookup"><span data-stu-id="12bf8-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="12bf8-104">Datentypen, Methodensignaturen und Mechanismen zur Behandlung von Fehlern variieren zwischen verwalteten und nicht verwalteten Objektmodellen.</span><span class="sxs-lookup"><span data-stu-id="12bf8-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="12bf8-105">Um die Interoperation zwischen .NET Framework-Komponenten und nicht verwaltetem Code sowie den Migrationspfad zu vereinfachen, verbirgt die Common Language Runtime die Unterschiede in diesen Objektmodellen vor jeweils Clients und Servern.</span><span class="sxs-lookup"><span data-stu-id="12bf8-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="12bf8-106">Code, der unter der Kontrolle der Runtime ausgeführt wird, wird als verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="12bf8-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="12bf8-107">Umgekehrt wird Code, der außerhalb der Runtime ausgeführt wird, wird als nicht verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="12bf8-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="12bf8-108">Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Windows API-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="12bf8-108">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="12bf8-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="12bf8-109">In this section</span></span>

[<span data-ttu-id="12bf8-110">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="12bf8-110">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="12bf8-111">Beschreibt, wie COM-Komponenten aus .NET Framework-Anwendungen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="12bf8-111">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="12bf8-112">Verfügbarmachen von .NET Framework-Komponenten in COM</span><span class="sxs-lookup"><span data-stu-id="12bf8-112">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="12bf8-113">Beschreibt, wie .NET Framework-Komponenten aus COM-Anwendungen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="12bf8-113">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="12bf8-114">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="12bf8-114">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="12bf8-115">Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="12bf8-115">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="12bf8-116">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="12bf8-116">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="12bf8-117">Beschreibt das Marshalling für COM-Interop sowie Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="12bf8-117">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="12bf8-118">Vorgehensweise: Zuordnen von HRESULT-Werten und Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="12bf8-118">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="12bf8-119">Beschreibt die Zuordnung zwischen Ausnahmen und HRESULTs</span><span class="sxs-lookup"><span data-stu-id="12bf8-119">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="12bf8-120">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="12bf8-120">COM Wrappers</span></span>](com-wrappers.md)  
<span data-ttu-id="12bf8-121">Beschreibt die von COM-Interop bereitgestellten Wrapper</span><span class="sxs-lookup"><span data-stu-id="12bf8-121">Describes the wrappers provided by COM interop.</span></span>

[<span data-ttu-id="12bf8-122">Typäquivalenz und eingebettete Interop-Typen</span><span class="sxs-lookup"><span data-stu-id="12bf8-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="12bf8-123">Beschreibt, wie die Typinformation für COM-Typen in Assemblys eingebettet wird und wie die Common Language Runtime die Äquivalenz von eingebetteten COM-Typen bestimmt</span><span class="sxs-lookup"><span data-stu-id="12bf8-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="12bf8-124">Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“</span><span class="sxs-lookup"><span data-stu-id="12bf8-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="12bf8-125">Beschreibt, wie primäre Interop-Assemblys mit *Tlbimp.exe* (Type Library Importer-Tool) erstellt werden</span><span class="sxs-lookup"><span data-stu-id="12bf8-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="12bf8-126">Vorgehensweise: Registrieren primärer Interopassemblys</span><span class="sxs-lookup"><span data-stu-id="12bf8-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="12bf8-127">Beschreibt, wie die primären Interop-Assemblys registriert werden, bevor Sie in Ihren Projekten auf diese verweisen können</span><span class="sxs-lookup"><span data-stu-id="12bf8-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="12bf8-128">COM-Interop ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="12bf8-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="12bf8-129">Beschreibt, wie COM-Interop Komponenten aktivieren kann, ohne die Windows-Registrierung zu verwenden</span><span class="sxs-lookup"><span data-stu-id="12bf8-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="12bf8-130">Vorgehensweise: Konfigurieren von .NET Framework-basierten COM-Komponenten für die Aktivierung ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="12bf8-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="12bf8-131">Beschreibt, wie ein Anwendungsmanifest erstellt wird und wie ein Komponentenmanifest erstellt und eingebettet wird</span><span class="sxs-lookup"><span data-stu-id="12bf8-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>
