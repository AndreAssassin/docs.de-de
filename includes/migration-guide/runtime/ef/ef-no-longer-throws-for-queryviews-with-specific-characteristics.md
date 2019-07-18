---
ms.openlocfilehash: bc33266bb2af639d7d0d1cb532ed73abd7f1ba9a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803275"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>Entity Framework löst für QueryViews bei bestimmten Zeichen keine Ausnahmen mehr aus

|   |   |
|---|---|
|Details|Entity Framework löst keine <xref:System.StackOverflowException?displayProperty=name>-Ausnahme mehr aus, wenn eine App eine Abfrage ausführt, die ein QueryView-Element mit einer 0..1-Navigationseigenschaft umfasst und versucht, die verwandten Entitäten als Teil der Abfrage zu verwenden. (Z.B. durch Aufrufen von <code>.Include(e =&gt; e.RelatedNavProp)</code>.)|
|Vorschlag|Diese Änderung betrifft nur Code, der QueryViews mit 1-0..1-Beziehungen verwendet, wenn Abfragen ausgeführt werden, die .Include aufrufen. Diese Änderung verbessert die Zuverlässigkeit und sollte für beinahe alle Apps transparent sein. Falls jedoch ein unerwünschtes Verhalten auftritt, können Sie dieses Feature deaktivieren, indem Sie den folgenden Eintrag im <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei einfügen:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.5.2|
|Typ|Laufzeit|

