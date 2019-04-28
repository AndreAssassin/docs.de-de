---
title: Benennen von Ressourcen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756883"
---
# <a name="naming-resources"></a><span data-ttu-id="3abd6-102">Benennen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3abd6-102">Naming Resources</span></span>
<span data-ttu-id="3abd6-103">Da der lokalisierbare Ressourcen als wären sie Eigenschaften über bestimmte Objekte verwiesen werden können, ähneln die Benennungsrichtlinien für Ressourcen Eigenschaft Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="3abd6-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="3abd6-104">**✓ DO** PascalCasing in Ressourcenschlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abd6-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="3abd6-105">**✓ DO** beschreibenden statt kurzer Bezeichner bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3abd6-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="3abd6-106">**X DO NOT** sprachspezifische Schlüsselwörter der wichtigsten CLR-Sprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abd6-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="3abd6-107">**✓ DO** nur alphanumerische Zeichen und Unterstriche enthalten, Benennen von Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abd6-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="3abd6-108">**✓ DO** die folgende Namenskonvention für die Ausnahme Nachricht Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3abd6-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="3abd6-109">Der Ressourcenbezeichner sollte der Name des Ausnahmetyps und einem kurzen Bezeichner der Ausnahme sein:</span><span class="sxs-lookup"><span data-stu-id="3abd6-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="3abd6-110">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="3abd6-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3abd6-111">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="3abd6-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abd6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3abd6-112">See also</span></span>

- [<span data-ttu-id="3abd6-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3abd6-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3abd6-114">Richtlinien für die Benennung</span><span class="sxs-lookup"><span data-stu-id="3abd6-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
