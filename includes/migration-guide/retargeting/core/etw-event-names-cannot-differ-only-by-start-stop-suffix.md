---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804044"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="41559-101">ETW-Ereignisnamen können sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden</span><span class="sxs-lookup"><span data-stu-id="41559-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="41559-102">Details</span><span class="sxs-lookup"><span data-stu-id="41559-102">Details</span></span>|<span data-ttu-id="41559-103">In .NET Framework 4.6 und 4.6.1 löst die Laufzeit <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen der Ereignisablaufverfolgung für Windows (ETW) sich lediglich durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden (z.B. wenn ein Ereignis mit <code>LogUser</code> benannt ist und das andere mit <code>LogUserStart</code>).</span><span class="sxs-lookup"><span data-stu-id="41559-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="41559-104">In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="41559-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="41559-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="41559-105">Suggestion</span></span>|<span data-ttu-id="41559-106">Stellen Sie sicher, dass zwei Ereignisnamen sich nicht nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden, um die Ausnahme zu verhindern. Diese Anforderung wird mit .NET Framework 4.6.2 entfernt. Die Laufzeit kann Ereignisnamen unterscheiden, die sich nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="41559-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="41559-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="41559-107">Scope</span></span>|<span data-ttu-id="41559-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="41559-108">Edge</span></span>|
|<span data-ttu-id="41559-109">Version</span><span class="sxs-lookup"><span data-stu-id="41559-109">Version</span></span>|<span data-ttu-id="41559-110">4.6</span><span class="sxs-lookup"><span data-stu-id="41559-110">4.6</span></span>|
|<span data-ttu-id="41559-111">Typ</span><span class="sxs-lookup"><span data-stu-id="41559-111">Type</span></span>|<span data-ttu-id="41559-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="41559-112">Retargeting</span></span>|
