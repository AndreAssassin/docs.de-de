---
ms.openlocfilehash: 3f88c8b80518aa65c082dc3da2d75b5221dd00f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774102"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>TextBox-/PasswordBox-Textauswahl von WPF folgt nicht den Systemfarben

|   |   |
|---|---|
|Details|In .NET Framework 4.7.1 und früheren Versionen konnten <code>System.Windows.Controls.TextBox</code> und <code>System.Windows.Controls.PasswordBox</code> von WPF nur eine Textauswahl aus der Adorner-Ebene rendern. In einigen Systemdesigns verdeckte dies Text, wodurch die Lesbarkeit erschwert wurde.  In .NET Framework 4.7.2 und höher besteht für Entwickler eine Option, ein nicht auf Adorner basierendes Auswahlrenderingschema zu aktivieren, das dieses Problem behebt.|
|Vorschlag|Ein Entwickler, die diese Änderung nutzen möchte, muss das folgende AppContext-Flag entsprechend festlegen.  Um dieses Feature nutzen zu können, muss die installierte Version von .NET Framework 4.7.2 oder höher sein. Um die nicht auf Adorner basierende Auswahl zu aktivieren, verwenden Sie das folgenden AppContext-Flag.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Neuzuweisung|
