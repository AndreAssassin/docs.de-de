---
ms.openlocfilehash: 4a31310551cea4250275843da3eae927bad23840
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236141"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a>Die App-Einstellung „dataAnnotations:dataTypeAttribute:disableRegEx“ ist in .NET Framework 4.7.2 standardmäßig aktiviert.

|   |   |
|---|---|
|Details|In .NET Framework 4.6.1 wurde die App-Einstellung <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> eingeführt, mir der Benutzer die Verwendung regulärer Ausdrücke in Datentypattributen (z.B. <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> und <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>) deaktivieren können. So können Sicherheitsrisiken wie mögliche Denial-of-Service-Angriffe mit bestimmten regulären Ausdrücken gesenkt werden.<br/>In .NET Framework 4.6.1 war diese App-Einstellung zur Verwendung von regulären Ausdrücken standardmäßig auf <code>false</code> festgelegt. Ab .NET Framework 4.7.2 wird dieser Konfigurationswert standardmäßig auf <code>true</code> festgelegt, um Sicherheitsrisiken für Webanwendungen für .NET Framework 4.7.2 und höher weiter zu senken.|
|Vorschlag|Wenn regulärer Ausdrücke in Ihrer Webanwendung nach dem Upgrade auf .NET Framework 4.7.2 nicht mehr funktionieren, können Sie den Wert der Einstellung <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> in <code>false</code> ändern, um wieder das alte Verhalten zu verwenden.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appsettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appsettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Laufzeit|
