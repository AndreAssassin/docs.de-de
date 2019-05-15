---
title: Identifizieren von Funktionen in DLLs
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c56712460d772426a2d8d6d328cba9bb03373d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648664"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="81e0f-102">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="81e0f-102">Identifying Functions in DLLs</span></span>
<span data-ttu-id="81e0f-103">Die Identität einer DLL-Funktion besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="81e0f-103">The identity of a DLL function consists of the following elements:</span></span>  
  
- <span data-ttu-id="81e0f-104">Funktionsname oder Ordinalzahl</span><span class="sxs-lookup"><span data-stu-id="81e0f-104">Function name or ordinal</span></span>  
  
- <span data-ttu-id="81e0f-105">Name der DLL-Datei, in der die Implementierung gefunden werden kann</span><span class="sxs-lookup"><span data-stu-id="81e0f-105">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="81e0f-106">Die Angabe der **MessageBox**-Funktion in der „User32.dll“ gibt beispielsweise die Funktion (**MessageBox**) und deren Speicherort (User32.dll, User32 oder user32) an.</span><span class="sxs-lookup"><span data-stu-id="81e0f-106">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="81e0f-107">Die Microsoft Windows-Anwendungsprogrammierschnittstelle (Windows-API) kann zwei Versionen jeder Funktion enthalten, die Zeichen und Zeichenfolgen verarbeitet: eine ANSI-Version mit 1-Byte-Zeichen und eine Unicode-Version mit 2-Byte-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="81e0f-107">The Microsoft Windows application programming interface (Windows API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="81e0f-108">Ohne Angabe wird der Zeichensatz, der durch das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld dargestellt wird, standardmäßig auf ANSI festgelegt.</span><span class="sxs-lookup"><span data-stu-id="81e0f-108">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="81e0f-109">Einige Funktionen können über mehr als zwei Versionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="81e0f-109">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="81e0f-110">**MessageBoxA** ist der ANSI-Einstiegspunkt für die **MessageBox**-Funktion. **MessageBoxW** ist die Unicode-Version.</span><span class="sxs-lookup"><span data-stu-id="81e0f-110">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="81e0f-111">Sie können Funktionsnamen für eine bestimmte DLL-Datei, z.B. „User32.dll“, auflisten, indem Sie eine Vielzahl von Befehlszeilentools ausführen.</span><span class="sxs-lookup"><span data-stu-id="81e0f-111">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="81e0f-112">Beispielsweise können Sie `dumpbin /exports user32.dll` oder `link /dump /exports user32.dll` verwenden, um Funktionsnamen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="81e0f-112">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="81e0f-113">Sie können eine nicht verwaltete Funktion innerhalb des Codes beliebig umbenennen, solange Sie den neuen Namen für den ursprünglichen Einstiegspunkt in der DLL zuordnen.</span><span class="sxs-lookup"><span data-stu-id="81e0f-113">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="81e0f-114">Anweisungen zur Umbenennung einer nicht verwalteten DLL-Funktion in verwaltetem Quellcode finden Sie unter [Angeben eines Einstiegspunktes](../../../docs/framework/interop/specifying-an-entry-point.md).</span><span class="sxs-lookup"><span data-stu-id="81e0f-114">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](../../../docs/framework/interop/specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="81e0f-115">Durch einen Plattformaufruf können Sie einen beträchtlichen Teil des Betriebssystems durch Aufrufen von Funktionen in der Windows-API und anderen DLLs steuern.</span><span class="sxs-lookup"><span data-stu-id="81e0f-115">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Windows API and other DLLs.</span></span> <span data-ttu-id="81e0f-116">Zusätzlich zur Windows-API stehen Ihnen über den Plattformaufruf zahlreiche andere APIs und DLLs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="81e0f-116">In addition to the Windows API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="81e0f-117">Die folgende Tabelle beschreibt einige häufig verwendete DLLs in der Windows-API.</span><span class="sxs-lookup"><span data-stu-id="81e0f-117">The following table describes several commonly used DLLs in the Windows API.</span></span>  
  
|<span data-ttu-id="81e0f-118">DLL</span><span class="sxs-lookup"><span data-stu-id="81e0f-118">DLL</span></span>|<span data-ttu-id="81e0f-119">Inhaltsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="81e0f-119">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="81e0f-120">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="81e0f-120">GDI32.dll</span></span>|<span data-ttu-id="81e0f-121">Funktionen für Graphics Device Interface (GDI) für Geräteausgaben, wie z.B. die für die Verwaltung der Zeichnung und Schriftart.</span><span class="sxs-lookup"><span data-stu-id="81e0f-121">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="81e0f-122">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="81e0f-122">Kernel32.dll</span></span>|<span data-ttu-id="81e0f-123">Betriebssystemfunktionen auf niedriger Ebene für die Verwaltung des Arbeitsspeichers und Ressourcenbehandlung.</span><span class="sxs-lookup"><span data-stu-id="81e0f-123">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="81e0f-124">User32.dll</span><span class="sxs-lookup"><span data-stu-id="81e0f-124">User32.dll</span></span>|<span data-ttu-id="81e0f-125">Windows-Verwaltungsfunktionen für Meldungsbehandlung, Timer, Menüs und Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="81e0f-125">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="81e0f-126">Eine vollständige Dokumentation der Windows-API finden Sie im Plattform SDK.</span><span class="sxs-lookup"><span data-stu-id="81e0f-126">For complete documentation on the Windows API, see the Platform SDK.</span></span> <span data-ttu-id="81e0f-127">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="81e0f-127">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e0f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81e0f-128">See also</span></span>

- [<span data-ttu-id="81e0f-129">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="81e0f-129">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="81e0f-130">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="81e0f-130">Specifying an Entry Point</span></span>](../../../docs/framework/interop/specifying-an-entry-point.md)
- [<span data-ttu-id="81e0f-131">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="81e0f-131">Creating a Class to Hold DLL Functions</span></span>](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="81e0f-132">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="81e0f-132">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="81e0f-133">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="81e0f-133">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
