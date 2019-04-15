---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236648"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="25291-101">Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5</span><span class="sxs-lookup"><span data-stu-id="25291-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="25291-102">Details</span><span class="sxs-lookup"><span data-stu-id="25291-102">Details</span></span>|<span data-ttu-id="25291-103">Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL.</span><span class="sxs-lookup"><span data-stu-id="25291-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="25291-104">Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.</span><span class="sxs-lookup"><span data-stu-id="25291-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="25291-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="25291-105">Suggestion</span></span>|<span data-ttu-id="25291-106">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="25291-106">This feature is disabled by default.</span></span> <span data-ttu-id="25291-107">Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="25291-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="25291-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="25291-108">Scope</span></span>|<span data-ttu-id="25291-109">Transparent</span><span class="sxs-lookup"><span data-stu-id="25291-109">Transparent</span></span>|
|<span data-ttu-id="25291-110">Version</span><span class="sxs-lookup"><span data-stu-id="25291-110">Version</span></span>|<span data-ttu-id="25291-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="25291-111">4.5.2</span></span>|
|<span data-ttu-id="25291-112">Typ</span><span class="sxs-lookup"><span data-stu-id="25291-112">Type</span></span>|<span data-ttu-id="25291-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="25291-113">Runtime</span></span>|
