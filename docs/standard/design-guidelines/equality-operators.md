---
title: Gleichheitsoperatoren
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960330"
---
# <a name="equality-operators"></a>Gleichheitsoperatoren
In diesem Abschnitt wird erläutert, das Überladen von Gleichheitsoperatoren und bezieht sich auf `operator==` und `operator!=` als Gleichheitsoperatoren.  
  
 **X DO NOT** die Gleichheitsoperatoren und die andere Überladung.  
  
 **✓ DO** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.  
  
 Dies bedeutet, dass häufig `Object.Equals` außer Kraft gesetzt werden, wenn die Operatoren überladen werden soll.  
  
 **X AVOID** Auslösen von Ausnahmen von Gleichheitsoperatoren.  
  
 Z. B. false zurück, wenn eines der Argumente null statt ist `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operatoren für Werttypen  
 **✓ DO** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.  
  
 In den meisten Programmiersprachen, es gibt keine standardmäßige Implementierung des `operator==` für Werttypen.  
  
## <a name="equality-operators-on-reference-types"></a>Gleichheitsoperatoren für Referenztypen  
 **X AVOID** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.  
  
 Viele Sprachen haben integrierte Operatoren für Verweistypen zulässig. Die integrierte Operatoren implementieren in der Regel der Verweisgleichheit und viele Entwickler sind oft überrascht, wenn das Standardverhalten in der Wertgleichheit geändert wird.  
  
 Dieses Problem ist für Verweistypen unveränderliche verringert, weil Unveränderlichkeit dadurch viel schwieriger zu beachten Sie, dass den Unterschied zwischen Verweisgleichheit und Wertgleichheit ist.  
  
 **X AVOID** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
