---
ms.openlocfilehash: 480cbdecd681408a7e1d6fa366e3f1a4b131ab42
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857540"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.  Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.  Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.|
|Vorschlag|Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

