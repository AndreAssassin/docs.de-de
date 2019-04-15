---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236066"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="b45a3-101">Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="b45a3-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b45a3-102">Details</span><span class="sxs-lookup"><span data-stu-id="b45a3-102">Details</span></span>|<span data-ttu-id="b45a3-103">In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b45a3-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="b45a3-104">Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b45a3-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="b45a3-105">Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.</span><span class="sxs-lookup"><span data-stu-id="b45a3-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="b45a3-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b45a3-106">Suggestion</span></span>|<span data-ttu-id="b45a3-107">Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.</span><span class="sxs-lookup"><span data-stu-id="b45a3-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="b45a3-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="b45a3-108">Scope</span></span>|<span data-ttu-id="b45a3-109">Gering</span><span class="sxs-lookup"><span data-stu-id="b45a3-109">Minor</span></span>|
|<span data-ttu-id="b45a3-110">Version</span><span class="sxs-lookup"><span data-stu-id="b45a3-110">Version</span></span>|<span data-ttu-id="b45a3-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b45a3-111">4.6.2</span></span>|
|<span data-ttu-id="b45a3-112">Typ</span><span class="sxs-lookup"><span data-stu-id="b45a3-112">Type</span></span>|<span data-ttu-id="b45a3-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b45a3-113">Runtime</span></span>|
|<span data-ttu-id="b45a3-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b45a3-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
