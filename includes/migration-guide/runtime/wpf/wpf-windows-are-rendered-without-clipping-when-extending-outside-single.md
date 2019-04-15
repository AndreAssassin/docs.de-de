---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234198"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="d9ea5-101">WPF-Fenster werden ohne Clipping gerendert, wenn diese die Größe eines einzelnen Monitors überschreiten</span><span class="sxs-lookup"><span data-stu-id="d9ea5-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d9ea5-102">Details</span><span class="sxs-lookup"><span data-stu-id="d9ea5-102">Details</span></span>|<span data-ttu-id="d9ea5-103">In .NET Framework 4.6, das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.</span><span class="sxs-lookup"><span data-stu-id="d9ea5-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="d9ea5-104">Dies unterscheidet sich von früheren Versionen von .NET Framework, bei denen WPF-Fenster beschnitten werden, die eine einzelne Anzeige überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d9ea5-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="d9ea5-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d9ea5-105">Suggestion</span></span>|<span data-ttu-id="d9ea5-106">Dieses Verhalten (ob ein Clipping angewendet wird oder nicht) kann explizit festgelegt werden, indem Sie das <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code>-Element von <code>&lt;appSettings&gt;</code> in der Konfigurationsdatei einer Anwendung verwenden oder indem Sie die <code>EnableMultiMonitorDisplayClipping</code>-Eigenschaft beim Starten der App festlegen.</span><span class="sxs-lookup"><span data-stu-id="d9ea5-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="d9ea5-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="d9ea5-107">Scope</span></span>|<span data-ttu-id="d9ea5-108">Gering</span><span class="sxs-lookup"><span data-stu-id="d9ea5-108">Minor</span></span>|
|<span data-ttu-id="d9ea5-109">Version</span><span class="sxs-lookup"><span data-stu-id="d9ea5-109">Version</span></span>|<span data-ttu-id="d9ea5-110">4.6</span><span class="sxs-lookup"><span data-stu-id="d9ea5-110">4.6</span></span>|
|<span data-ttu-id="d9ea5-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d9ea5-111">Type</span></span>|<span data-ttu-id="d9ea5-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d9ea5-112">Runtime</span></span>|
