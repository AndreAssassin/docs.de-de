---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804031"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="3b6ba-101">ConcurrentQueue\<T>.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben</span><span class="sxs-lookup"><span data-stu-id="3b6ba-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3b6ba-102">Details</span><span class="sxs-lookup"><span data-stu-id="3b6ba-102">Details</span></span>|<span data-ttu-id="3b6ba-103">In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).</span><span class="sxs-lookup"><span data-stu-id="3b6ba-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="3b6ba-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3b6ba-104">Suggestion</span></span>|<span data-ttu-id="3b6ba-105">Dieses Problem wurde in .NET Framework 4.5.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="3b6ba-106">Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.</span><span class="sxs-lookup"><span data-stu-id="3b6ba-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="3b6ba-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="3b6ba-107">Scope</span></span>|<span data-ttu-id="3b6ba-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="3b6ba-108">Major</span></span>|
|<span data-ttu-id="3b6ba-109">Version</span><span class="sxs-lookup"><span data-stu-id="3b6ba-109">Version</span></span>|<span data-ttu-id="3b6ba-110">4.5</span><span class="sxs-lookup"><span data-stu-id="3b6ba-110">4.5</span></span>|
|<span data-ttu-id="3b6ba-111">Typ</span><span class="sxs-lookup"><span data-stu-id="3b6ba-111">Type</span></span>|<span data-ttu-id="3b6ba-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3b6ba-112">Runtime</span></span>|
|<span data-ttu-id="3b6ba-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3b6ba-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
