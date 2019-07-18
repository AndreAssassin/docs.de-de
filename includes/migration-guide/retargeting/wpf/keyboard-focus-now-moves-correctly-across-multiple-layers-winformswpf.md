---
ms.openlocfilehash: 3bde64b80e5dcfe98bbf598700b6d7004e3c3c9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774040"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Der Tastaturfokus bewegt sich jetzt ordnungsgemäß über mehrere Ebenen von WinForms-/WPF-Hosting

|   |   |
|---|---|
|Details|Nehmen Sie als Beispiel eine WPF-Anwendung, die ein WinForms-Steuerelement hostet, das wiederum WPF-Steuerelemente hostet. Benutzer können die WinForms-Ebene möglicherweise nicht mit der TABULATORTASTE verlassen, wenn das erste oder letzte Steuerelement in diese Ebene <code>System.Windows.Forms.Integration.ElementHost</code> von WPF ist. Diese Änderung behebt dieses Problem, und Benutzer können die WinForms-Ebene jetzt mit der TABULATORTASTE verlassen. Automatisierte Anwendungen, die erfordern, dass der Fokus die WinForms-Ebene nie verlässt, funktionieren möglicherweise nicht mehr wie erwartet.|
|Vorschlag|Ein Entwickler, der diese Änderung für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, kann die folgende Gruppe von AppContext-Flags auf FALSE festlegen, damit die Änderung aktiviert wird.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>WPF-Anwendungen müssen alle frühen Barrierefreiheitsverbesserungen aktivieren, um die späteren Verbesserungen abrufen zu können. Das heißt, die <code>Switch.UseLegacyAccessibilityFeatures</code>- und <code>Switch.UseLegacyAccessibilityFeatures.2</code>-Schalter müssen festgelegt werden. Ein-Entwickler, der die vorherige Funktionalität für .NET 4.7.2 oder höher benötigt, kann das folgende AppContext-Flag auf TRUE festlegen, damit die Änderung deaktiviert wird.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|
