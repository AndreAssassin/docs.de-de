---
title: Frameworkentwurfsrichtlinien
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: c20430f9cdcd71cc2e178d38aeed48f9fa4e75c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026379"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="3a62c-102">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3a62c-102">Framework Design Guidelines</span></span>
<span data-ttu-id="3a62c-103">Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die zu erweitern, und interagieren mit .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a62c-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="3a62c-104">Ziel ist es, sicherzustellen, dass API-Konsistenz und benutzerfreundlichkeit durch die Bereitstellung eines einheitlichen Programmiermodell, das unabhängig von der Programmiersprache, die für die Entwicklung verwendet Bibliotheks-Designer-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="3a62c-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="3a62c-105">Es wird empfohlen, dass Sie diese Entwurfsrichtlinien halten, bei der Entwicklung von Klassen und Komponenten, die .NET Framework zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3a62c-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="3a62c-106">Inkonsistente Bibliotheksentwurf negativ wirkt sich auf Entwicklerproduktivität und ungern.</span><span class="sxs-lookup"><span data-stu-id="3a62c-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="3a62c-107">Die Richtlinien werden als einfache Empfehlungen präsentiert organisiert `Do`, `Consider`, `Avoid`, und `Do not`.</span><span class="sxs-lookup"><span data-stu-id="3a62c-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="3a62c-108">Diese Richtlinien sollen Entwickler verstehen, die Kompromisse zwischen verschiedenen Lösungen helfen.</span><span class="sxs-lookup"><span data-stu-id="3a62c-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="3a62c-109">Es gibt möglicherweise Situationen, in denen guten Bibliotheksentwurf erfordert, dass Sie diese Richtlinien für den Entwurf verletzt.</span><span class="sxs-lookup"><span data-stu-id="3a62c-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="3a62c-110">Einem solchen Fall dürfte selten passieren, und es ist wichtig, dass einen deutliches und überzeugenden Grund für Ihre Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="3a62c-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="3a62c-111">Diese Richtlinien sind ein Auszug aus dem Buch *Framework-Entwurfsrichtlinien vorgestellt: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET Bibliotheken, 2. Auflage*, indem Sie Krzysztof Cwalina und Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="3a62c-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a62c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3a62c-112">In This Section</span></span>  
 [<span data-ttu-id="3a62c-113">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="3a62c-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="3a62c-114">Enthält Richtlinien zum Benennen von Assemblys, Namespaces, Typen und Member in Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="3a62c-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="3a62c-115">Richtlinien für den Entwurf von Typen</span><span class="sxs-lookup"><span data-stu-id="3a62c-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="3a62c-116">Enthält Richtlinien für die Verwendung von statischen und abstrakte Klassen, Schnittstellen, Enumerationen, Strukturen und andere Typen.</span><span class="sxs-lookup"><span data-stu-id="3a62c-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="3a62c-117">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="3a62c-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="3a62c-118">Enthält Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Felder, Ereignisse, Operatoren und Parameter.</span><span class="sxs-lookup"><span data-stu-id="3a62c-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="3a62c-119">Entwerfen für Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="3a62c-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="3a62c-120">Beschreibt Mechanismen zur Erweiterbarkeit wie z. B. Unterklassen, die mithilfe von Ereignissen, virtuelle Member und Rückrufe aus, und erläutert, wie auf die Mechanismen, die am besten des Frameworks Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3a62c-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="3a62c-121">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3a62c-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="3a62c-122">Beschreibt Entwurfsrichtlinien für das Entwerfen, auslösen und Abfangen von Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="3a62c-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="3a62c-123">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3a62c-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="3a62c-124">Enthält Richtlinien zum verwenden allgemeine Typen wie Arrays, Attribute und Sammlungen, zur Unterstützung der Serialisierung und Überladen von Gleichheitsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="3a62c-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="3a62c-125">Allgemeine Entwurfsmuster</span><span class="sxs-lookup"><span data-stu-id="3a62c-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="3a62c-126">Enthält Richtlinien zur Auswahl und Implementierung von Abhängigkeitseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3a62c-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="3a62c-127">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3a62c-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3a62c-128">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="3a62c-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a62c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a62c-129">See also</span></span>

- [<span data-ttu-id="3a62c-130">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3a62c-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="3a62c-131">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="3a62c-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
