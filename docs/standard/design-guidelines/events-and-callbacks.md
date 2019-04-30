---
title: Ereignisse und Rückrufe
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
author: KrzysztofCwalina
ms.openlocfilehash: 3609d6ac4847cb081740fd698869df4976f83f8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960394"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="51321-102">Ereignisse und Rückrufe</span><span class="sxs-lookup"><span data-stu-id="51321-102">Events and Callbacks</span></span>
<span data-ttu-id="51321-103">Rückrufe sind Erweiterungspunkte, die ein Framework Rückruf in Benutzercode durch einen Delegaten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="51321-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="51321-104">Diese Delegaten werden in der Regel für das Framework über einen Parameter einer Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="51321-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="51321-105">Ereignisse sind ein Sonderfall der Rückrufe, der bequeme, einheitliche Syntax unterstützt wird, für den Delegaten (ein Ereignishandler) angeben.</span><span class="sxs-lookup"><span data-stu-id="51321-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="51321-106">Darüber hinaus bieten die Anweisungsvervollständigung und Designer von Visual Studio Hilfe bei der Verwendung von Ereignis-basierten APIs.</span><span class="sxs-lookup"><span data-stu-id="51321-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="51321-107">(Finden Sie unter [Ereignisentwurf](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="51321-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="51321-108">**✓ CONSIDER** Verwendung von Rückrufen Benutzer geben Sie benutzerdefinierten Code, der durch das Framework ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="51321-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="51321-109">**✓ CONSIDER** Ereignisse verwenden, um Benutzern das Anpassen des Verhaltens von einem Framework ohne die Notwendigkeit, um zu verstehen, eines objektorientierten Entwurfs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="51321-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="51321-110">**✓ DO** plain Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und mit Visual Studio-Anweisungsvervollständigung integriert sind.</span><span class="sxs-lookup"><span data-stu-id="51321-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="51321-111">**X AVOID** Rückrufe in leistungsabhängigen-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="51321-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="51321-112">**✓ DO** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs mit Rückrufe zu definieren.</span><span class="sxs-lookup"><span data-stu-id="51321-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="51321-113">`Func<...>` und `Action<...>` generische Delegaten darstellen.</span><span class="sxs-lookup"><span data-stu-id="51321-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="51321-114">`Expression<...>` Stellt Funktionsdefinitionen, die kompiliert und anschließend zur Laufzeit kann aber auch aufgerufen werden können, serialisiert und an remote-Prozesse übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="51321-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="51321-115">**✓ DO** messen und Verstehen von Auswirkungen auf die Leistung der Verwendung von `Expression<...>`, anstatt `Func<...>` und `Action<...>` Delegaten.</span><span class="sxs-lookup"><span data-stu-id="51321-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="51321-116">`Expression<...>` Typen sind in den meisten Fällen ist logisch äquivalent zur `Func<...>` und `Action<...>` Delegaten.</span><span class="sxs-lookup"><span data-stu-id="51321-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="51321-117">Der Hauptunterschied zwischen diesen besteht darin, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen; Ausdrücke werden für Fälle gedacht, bei denen es vorteilhaft und zum Auswerten des Ausdrucks in einer remote-Prozess oder Computer möglich.</span><span class="sxs-lookup"><span data-stu-id="51321-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="51321-118">**✓ DO** verstehen, dass durch den Aufruf eines Delegaten, beliebigen Code ausführen und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität Verarbeitungsverhaltens.</span><span class="sxs-lookup"><span data-stu-id="51321-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="51321-119">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="51321-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="51321-120">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="51321-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51321-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51321-121">See also</span></span>

- [<span data-ttu-id="51321-122">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="51321-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="51321-123">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="51321-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
