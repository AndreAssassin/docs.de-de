---
ms.openlocfilehash: 4340ed7444681b4601dea50c93926b0ee0c07eec
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134112"
---

<span data-ttu-id="6fb3b-101">Die Pakete, die dem Paket-Manager-Feed hinzugefügt werden, werden in einem Format benannt, das gehackt werden kann: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="6fb3b-102">**Produkt**</span><span class="sxs-lookup"><span data-stu-id="6fb3b-102">**product**</span></span>\
<span data-ttu-id="6fb3b-103">Der Typ des zu installierenden .NET-Produkts.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-103">The type of .NET product to install.</span></span> <span data-ttu-id="6fb3b-104">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6fb3b-104">Valid options are:</span></span>

  - <span data-ttu-id="6fb3b-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="6fb3b-105">dotnet</span></span>
  - <span data-ttu-id="6fb3b-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="6fb3b-106">aspnetcore</span></span>

- <span data-ttu-id="6fb3b-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6fb3b-107">**type**</span></span>\
<span data-ttu-id="6fb3b-108">Wählt das SDK oder die Runtime aus.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="6fb3b-109">Folgende Optionen sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6fb3b-109">Valid options are:</span></span>

  - <span data-ttu-id="6fb3b-110">SDK</span><span class="sxs-lookup"><span data-stu-id="6fb3b-110">sdk</span></span>
  - <span data-ttu-id="6fb3b-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6fb3b-111">runtime</span></span>

- <span data-ttu-id="6fb3b-112">**Version**</span><span class="sxs-lookup"><span data-stu-id="6fb3b-112">**version**</span></span>\
<span data-ttu-id="6fb3b-113">Die Version des zu installierenden SDK oder der zu installierenden Runtime.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="6fb3b-114">In diesem Artikel erhalten Sie stets die Anweisungen für die neueste unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="6fb3b-115">Gültige Optionen sind alle veröffentlichte Versionen, wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="6fb3b-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="6fb3b-116">3.1</span><span class="sxs-lookup"><span data-stu-id="6fb3b-116">3.1</span></span>
  - <span data-ttu-id="6fb3b-117">3.0</span><span class="sxs-lookup"><span data-stu-id="6fb3b-117">3.0</span></span>
  - <span data-ttu-id="6fb3b-118">2.1</span><span class="sxs-lookup"><span data-stu-id="6fb3b-118">2.1</span></span>

  <span data-ttu-id="6fb3b-119">Es ist möglich, dass das SDK bzw. die Runtime, das/die Sie herunterladen möchten, für Ihre Linux-Distribution nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="6fb3b-120">Eine Liste der unterstützten Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="6fb3b-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="6fb3b-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6fb3b-121">Examples</span></span>

- <span data-ttu-id="6fb3b-122">Installieren der ASP.NET Core 3.1-Runtime: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="6fb3b-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="6fb3b-123">Installieren der .NET Core 2.1-Runtime: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="6fb3b-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="6fb3b-124">Installieren des .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span><span class="sxs-lookup"><span data-stu-id="6fb3b-124">Install the .NET Core 3.1 SDK: `dotnet-sdk-3.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="6fb3b-125">Fehlendes Paket</span><span class="sxs-lookup"><span data-stu-id="6fb3b-125">Package missing</span></span>

<span data-ttu-id="6fb3b-126">Wenn die Kombination aus Paket und Version nicht funktioniert, ist sie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="6fb3b-127">Beispielsweise gibt es keine ASP.NET Core SDK, die SDK-Komponenten sind in der .NET Core SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="6fb3b-128">Der Wert `aspnetcore-sdk-2.2` ist falsch und sollte `dotnet-sdk-2.2` lauten.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="6fb3b-129">Eine Liste der von .NET Core unterstützten Linux-Distributionen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="6fb3b-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
