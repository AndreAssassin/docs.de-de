---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ea4c8110a8f820e0c6204fbd22b3d5b747709fba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61950461"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="6737c-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="6737c-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="6737c-103">Das PeerMaintainer-Modul führt einen bestimmten Vorgang (Details innerhalb des Ablaufverfolgungsnachrichtentexts) aus.</span><span class="sxs-lookup"><span data-stu-id="6737c-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="6737c-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6737c-104">Description</span></span>  
 <span data-ttu-id="6737c-105">Diese Ablaufverfolgung tritt während verschiedener PeerMaintainer-Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="6737c-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="6737c-106">PeerMaintainer ist eine interne Komponente von PeerNode.</span><span class="sxs-lookup"><span data-stu-id="6737c-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="6737c-107">Jede Minute &amp;#8211; oder nach 32&amp;#160;empfangenen Nachrichten &amp;#8211; wird eine LinkUtility-Nachricht an die Nachbarn gesendet. Diese Nachricht enthält eine Statistik mit der Anzahl der ausgetauschten Nachrichten sowie mit Informationen dazu, wie viele der Nachrichten nützlich waren (also keine Duplikate und nicht manipuliert).</span><span class="sxs-lookup"><span data-stu-id="6737c-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="6737c-108">Dadurch lässt sich das Verknüpfungsprogramm eines bestimmten Nachbarn ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6737c-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="6737c-109">Etwa alle fünf Minuten überprüft der Maintainer die Integrität der Nachbarverbindungen.</span><span class="sxs-lookup"><span data-stu-id="6737c-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="6737c-110">Übersteigt die Anzahl von Nachbarverbindungen die Idealmenge, werden die am wenigsten nützlichen Verbindungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="6737c-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="6737c-111">Sind nicht genügend Verbindungen verfügbar, werden vom Maintainer neue Verbindungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="6737c-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6737c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6737c-112">See also</span></span>

- [<span data-ttu-id="6737c-113">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6737c-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6737c-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6737c-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6737c-115">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6737c-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
