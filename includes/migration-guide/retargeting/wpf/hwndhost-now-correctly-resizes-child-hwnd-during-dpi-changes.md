---
ms.openlocfilehash: d374ded6a29ce815beeb26505010563a26d978e8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803471"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a>HwndHost ändert nun die Größe eines untergeordneten HWND bei DPI-Änderungen ordnungsgemäß

|   |   |
|---|---|
|Details|Wenn WPF im PMA-Modus (Per-Monitor Aware) ausgeführt wurde, wurde in .NET Framework 4.7.2 und früheren Versionen die Größe von in <xref:System.Windows.Interop.HwndHost> gehosteten Steuerelementen nach DPI-Änderungen, also beispielsweise beim Verschieben von Anwendungen von einem Monitor zu einem anderen, nicht ordnungsgemäß geändert. Mit dieser Korrektur wird sichergestellt, dass die Größe von gehosteten Steuerelementen ordnungsgemäß geändert wird.|
|Vorschlag|Damit die Anwendung von diesen Änderungen profitiert, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Zudem muss dieses Verhalten aktiviert werden, indem der folgende [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) im <code>&lt;runtime&gt;</code>-Abschnitt der Konfigurationsdatei der Anwendung wie im folgenden Beispiel auf <code>false</code> festgelegt wird.<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Hauptversion|
|Version|4.8|
|Typ|Neuzuweisung|

