---
ms.openlocfilehash: ce7e2db3f74ec24f47b1c224335451c997c4c349
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804342"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>WCF-Bindung mit dem TransportWithMessageCredential-Sicherheitsmodus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.1 kann die WCF-Bindung, die den TransportWithMessageCredential-Sicherheitsmodus verwendet, so eingerichtet werden, dass Nachrichten mit nicht signierten &quot;to&quot;-Headern für asymmetrische Sicherheitsschlüssel empfangen werden. Standardmäßig werden nicht signierte &quot;to&quot;-Header in .NET Framework 4.6.1 weiter abgelehnt. Sie werden nur akzeptiert, wenn eine Anwendung unter Verwendung des Switch.System.ServiceModel.AllowUnsignedToHeader-Konfigurationsschalters diesen neuen Vorgangsmodus aktiviert.|
|Vorschlag|Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.<br/>Verwenden Sie die folgende Konfigurationseinstellung, um zu steuern, ob das neue Verhalten verwendet werden soll:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Transparent|
|Version|4.6.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|

