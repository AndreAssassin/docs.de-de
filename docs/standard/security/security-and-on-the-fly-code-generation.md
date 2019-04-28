---
title: Sicherheit und dynamische Codegenerierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffb1081c80c31353ad38080ae16ef9f8a74b5481
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860541"
---
# <a name="security-and-on-the-fly-code-generation"></a>Sicherheit und dynamische Codegenerierung
Einige Bibliotheken funktionieren, indem sie Code generieren und diesen ausführen, um einen Vorgang für den Aufrufer durchzuführen. Das Grundproblem besteht darin, Code auf Veranlassung eines weniger vertrauenswürdigen Codes zu generieren und den generierten Code mit einer höheren Vertrauensebene auszuführen. Das Problem ist noch gravierender, wenn der Aufrufer die Codegenerierung beeinflussen kann. Deshalb müssen Sie sicherstellen, dass nur Code generiert wird, den Sie als sicher erachten.  
  
 Sie müssen jederzeit genau wissen, welchen Code Sie erstellen. Dies bedeutet, dass Sie unbedingte Kontrolle über alle Werte haben müssen, die von einem Benutzer stammen, egal, ob diese Werte in Anführungszeichen eingeschlossene Zeichenfolgen (die mit Escapezeichen versehen werden sollten, damit sie keine unerwarteten Codeelemente enthalten können), Bezeichner (die daraufhin überprüft werden sollten, dass sie gültige Bezeichner sind) oder etwas anderes sind. Bezeichner können gefährlich sein, da eine kompilierte Assembly so geändert werden kann, dass ihre Bezeichner ungewöhnliche Zeichen enthalten, die die Assembly wahrscheinlich unbrauchbar machen (obwohl dies selten ein Sicherheitsrisiko darstellt).  
  
 Es wird empfohlen, dass Sie Code mit Reflektionsausgabe generieren, wodurch sich viele dieser Probleme vermeiden lassen.  
  
 Wenn Sie den Code kompilieren, sollten Sie überlegen, ob für Malware eine Möglichkeit besteht, den Code zu ändern. Gibt es ein kleines Zeitfenster, in dem Malware den Quellcode auf dem Datenträger ändern kann, bevor der Quellcode vom Compiler gelesen wird oder bevor Ihr Code die DLL-Datei lädt? Ist dies der Fall, müssen Sie das Verzeichnis, das diese Dateien enthält, entsprechend mit einer Zugriffssteuerungsliste im Dateisystem schützen.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
