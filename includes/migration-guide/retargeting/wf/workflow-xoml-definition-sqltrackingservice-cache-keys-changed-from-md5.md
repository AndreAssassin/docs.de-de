---
ms.openlocfilehash: 47aa67096f8dcd250521d9c34dde97cb2eb368d7
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803489"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>Änderung von XOML-Workflowdefinition und ndSqlTrackingService-Cacheschlüssel von MD5 in SHA256

|   |   |
|---|---|
|Details|Die Workflowlaufzeit verwaltet einen Cache mit in XOML definierten Workflowdefinitionen. SqlTrackingService verwaltet ebenfalls einen Cache, der mit Zeichenfolgen verschlüsselt ist. Diese Caches werden nach Werten verschlüsselt, die den Hashwert der Prüfsumme enthalten. In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.8 wird der Algorithmus SHA256 verwendet. Diese Änderung bringt kein Kompatibilitätsproblem mit sich, da die Werte bei jedem Start von Workflowlaufzeit und SqlTrackingService neu berechnet werden. Kunden haben jedoch die Möglichkeit, ggf. zur Verwendung des älteren Hashalgorithmus zurückzukehren.|
|Vorschlag|Wenn diese Änderung beim Ausführen von Workflows ein Problem darstellt, legen Sie einen oder beide <code>AppContext</code>-Switches auf „True“ fest:<ul><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;</li><li>&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;</li></ul>In Code:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>Oder in der Konfigurationsdatei der Anwendung, die das <xref:System.Workflow.Runtime.WorkflowRuntime>-Objekt erstellt:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.8|
|Typ|Neuzuweisung|

