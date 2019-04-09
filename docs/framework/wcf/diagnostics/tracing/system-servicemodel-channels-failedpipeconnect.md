---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 472821d880433cd6a3292838a48bcb0b5bb34c43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152294"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="48cfc-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="48cfc-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="48cfc-103">Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="48cfc-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="48cfc-104">Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.</span><span class="sxs-lookup"><span data-stu-id="48cfc-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="48cfc-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48cfc-105">Description</span></span>  
 <span data-ttu-id="48cfc-106">Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="48cfc-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="48cfc-107">Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="48cfc-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="48cfc-108">Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="48cfc-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48cfc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48cfc-109">See also</span></span>

- [<span data-ttu-id="48cfc-110">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="48cfc-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="48cfc-111">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="48cfc-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="48cfc-112">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="48cfc-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
