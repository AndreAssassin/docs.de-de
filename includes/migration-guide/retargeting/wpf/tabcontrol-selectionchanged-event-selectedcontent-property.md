---
ms.openlocfilehash: 923105114c9e8da02c61c842cc02bed1ead3eddc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236467"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>SelectionChanged-Ereignis und SelectedContent-Eigenschaft von „TabControl“

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.1 aktualisiert <xref:System.Windows.Controls.TabControl> den Wert der <xref:System.Windows.Controls.TabControl.SelectedContent>-Eigenschaft, bevor das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>-Ereignis ausgelöst wird, wenn die Auswahl geändert wird. In .NET Framework 4.7 und früher wurde das Update für „SelectedContent“ nach dem Ereignis durchgeführt.|
|Vorschlag|Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei Folgendes hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.1|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
