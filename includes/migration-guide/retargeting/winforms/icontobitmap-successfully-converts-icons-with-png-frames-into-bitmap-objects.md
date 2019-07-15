---
ms.openlocfilehash: 9c2a8eca3f4498906cf703ff3b8ffb7336ff7a1b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804617"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap konvertiert Symbole mit PNG-Frames erfolgreich in Bitmap-Objekte

|   |   |
|---|---|
|Details|Beginnend mit den Apps für .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode Symbole mit PNG-Bildern erfolgreich in „Bitmap“-Objekte.<p/>In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgelegt sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das „Icon“-Objekt PNG-Bilder aufweist.<p/>Diese Änderung betrifft Apps, die für .NET Framework 4.6 neu kompiliert werden und eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein „Icon“-Objekt PNG-Bilder aufweist. Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.|
|Vorschlag|Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum <code>&lt;runtime&gt;</code>-Abschnitt Ihrer app.config-Datei hinzufügen:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>Wenn die Datei „app.config“ bereits das <code>AppContextSwitchOverrides</code>-Element enthält, muss der neue Wert wie folgt mit dem Attribut zusammengeführt werden:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.6|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|

