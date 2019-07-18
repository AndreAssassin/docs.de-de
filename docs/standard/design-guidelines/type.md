---
title: Richtlinien für den Entwurf von Typen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: KrzysztofCwalina
ms.openlocfilehash: 16f2a095f461a406eedbd2b34b0c91d3ac43bbe5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650101"
---
# <a name="type-design-guidelines"></a>Richtlinien für den Entwurf von Typen
Aus Sicht der CLR stehen nur zwei Kategorien von Typen, Verweistypen und Werttypen, jedoch für eine Erläuterung zu Framework-Designs, einzuteilen Typen in logische Gruppen, die jeweils über eigene bestimmte Regeln.  
  
 Klassen sind grundsätzlich von Verweistypen. Sie stellen den Großteil der Typen in den meisten Frameworks. Klassen Schulden ihre Beliebtheit, um die umfassenden Satz von objektorientierten Funktionen, die sie unterstützen und ihre allgemeine Anwendbarkeit. Abstrakte Klassen und Basisklassen sind spezielle logische Gruppen, die im Zusammenhang mit der Erweiterbarkeit.  
  
 Schnittstellen sind von Typen, die implementiert werden, können sowohl Verweistypen und Werttypen. Sie können daher als Stamm der polymorphen Hierarchien von Verweistypen und Werttypen dienen. Darüber hinaus können Schnittstellen, mehrfachvererbung, zu simulieren, die von der CLR nicht systemintern unterstützt wird, verwendet werden.  
  
 Strukturen sind grundsätzlich von Werttypen und für kleine, einfache Typen, ähnlich wie Sprachprimitive reserviert werden soll.  
  
 Enumerationen sind ein Sonderfall von Werttypen, die zum Definieren von kurzen Sätze von Werten, z. B. Tage der Woche, konsolenfarben usw. verwendet.  
  
 Statische Klassen sind Typen, die Container für statische Member erstellt werden soll. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.  
  
 Delegaten, Ausnahmen, Attribute, Arrays und Sammlungen sind alle Sonderfälle von Verweistypen, die für einen bestimmten Verwendungszweck vorgesehen und Richtlinien für Design und Nutzung in diesem Buch an anderer Stelle erörtert werden.  
  
 **✓ DO** stellen Sie sicher, dass jeder Typ einen genau definierten Satz verwandter Elemente, nicht nur eine zufällige Sammlung von unabhängigen Funktionalität ist.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Entwurf abstrakter Klassen](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md)  
 [Schnittstellenentwurf](../../../docs/standard/design-guidelines/interface.md)  
 [Strukturentwurf](../../../docs/standard/design-guidelines/struct.md)  
 [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md)  
 [Geschachtelte Typen](../../../docs/standard/design-guidelines/nested-types.md)  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
