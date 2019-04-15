---
ms.openlocfilehash: abb89099c4c8a5d9c0e55ef8f357faf44e75b045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234189"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Die Rechtschreibüberprüfung in textfähigen WPF-Steuerelementen funktioniert unter Windows 10 nicht für die Sprachen, die nicht in der Liste der Eingabesprachen in dem Betriebssystem aufgeführt sind

|   |   |
|---|---|
|Details|Bei einem Windows 10-Betriebssystem kann es sein, dass die Rechtschreibüberprüfung für textfähige WPF-Steuerelemente nicht funktioniert, da die plattformspezifischen Funktionen zur Rechtsschreibüberprüfung nur für die Sprachen verfügbar sind, die in der Liste mit den Eingabesprachen aufgeführt sind. Wenn in Windows 10 eine Sprache zu der Liste mit verfügbaren Tastaturen hinzugefügt wird, lädt Windows automatisch ein passendes Feature-On-Demand-Paket herunter, das Funktion zur Rechtschreibüberprüfung enthält, und installiert dieses. Durch das Hinzufügen der Sprache zur Eingabesprachenliste wird die Rechtschreibprüfung unterstützt.|
|Vorschlag|Beachten Sie, das die Sprache oder der Text, deren bzw. dessen Rechtschreibung überprüft werden muss, als Eingabesprache hinzugefügt werden muss, damit die Rechtschreibüberprüfung in Windows 10 funktioniert.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit|
