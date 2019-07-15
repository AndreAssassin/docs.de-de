---
ms.openlocfilehash: 480cbdecd681408a7e1d6fa366e3f1a4b131ab42
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857540"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="3ec29-101">Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec29-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3ec29-102">Details</span><span class="sxs-lookup"><span data-stu-id="3ec29-102">Details</span></span>|<span data-ttu-id="3ec29-103">In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="3ec29-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="3ec29-104">Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ec29-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="3ec29-105">Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.</span><span class="sxs-lookup"><span data-stu-id="3ec29-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="3ec29-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3ec29-106">Suggestion</span></span>|<span data-ttu-id="3ec29-107">Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.</span><span class="sxs-lookup"><span data-stu-id="3ec29-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="3ec29-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="3ec29-108">Scope</span></span>|<span data-ttu-id="3ec29-109">Gering</span><span class="sxs-lookup"><span data-stu-id="3ec29-109">Minor</span></span>|
|<span data-ttu-id="3ec29-110">Version</span><span class="sxs-lookup"><span data-stu-id="3ec29-110">Version</span></span>|<span data-ttu-id="3ec29-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3ec29-111">4.6.2</span></span>|
|<span data-ttu-id="3ec29-112">Typ</span><span class="sxs-lookup"><span data-stu-id="3ec29-112">Type</span></span>|<span data-ttu-id="3ec29-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3ec29-113">Runtime</span></span>|
|<span data-ttu-id="3ec29-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3ec29-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

