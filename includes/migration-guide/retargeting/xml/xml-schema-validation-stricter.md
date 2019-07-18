---
ms.openlocfilehash: ef0381dc2ce4373b2a62e8ebefa44152059ca332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234694"
---
### <a name="xml-schema-validation-is-stricter"></a>Die XML-Schemaüberprüfung ist genauer

|   |   |
|---|---|
|Details|In .NET Framework 4.5 ist die XML-Schemaüberprüfung genauer. Wenn Sie xsd:anyURI verwenden, um einen URI wie ein mailto-Protokoll zu überprüfen, tritt bei der Validierung ein Fehler auf, wenn der URI Leerzeichen enthält. In früheren Versionen von .NET Framework war die Validierung erfolgreich. Die Änderung betrifft nur Anwendungen, die auf .NET Framework 4.5 ausgerichtet sind.|
|Vorschlag|Wenn eine weniger genaue Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.0 von .NET Framework ausgerichtet werden. Bei einer Neuausrichtung auf .NET Framework 4.5 sollte jedoch ein Code Review erfolgen, um sicherzustellen, dass ungültige URIs (mit Leerzeichen) nicht als Attributwerte mit dem Datentyp „anyURI“ erwartet werden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|
