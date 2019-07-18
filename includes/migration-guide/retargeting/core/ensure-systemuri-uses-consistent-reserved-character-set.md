---
ms.openlocfilehash: 2ec5224b1ab16c05f6f942f6084f1ab105b71b0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774022"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Sicherstellen, dass System.Uri einen konsistenten reservierten Zeichensatz verwendet

|   |   |
|---|---|
|Details|In <xref:System.Uri?displayProperty=fullName> sind bestimmte prozentcodierte Zeichen, die manchmal decodiert wurden, jetzt konsistent linkscodiert. Dies tritt für die Eigenschaften und Methoden auf, die auf die Pfad-, Abfrage-, Fragment- oder Benutzerinformationenkomponenten des URIs zugreifen. Das Verhalten ändert sich nur, wenn die beiden folgenden Bedingungen erfüllt sind:<ul><li>Der URI enthält die codierte Form eines der folgenden reservierten Zeichen: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> oder <code>*</code>.</li><li>Der URI enthält ein Unicode- oder nicht codiertes reserviertes Zeichen. Wenn beide oben genannten Kriterien erfüllt sind, werden die codierten reservierten Zeichen linkscodiert. In früheren Versionen von .NET Framework wurden sie decodiert.</li></ul>|
|Vorschlag|Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist dieses neue Decodierungsverhalten standardmäßig aktiviert. Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist das neue Decodierungsverhalten standardmäßig deaktiviert. Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
