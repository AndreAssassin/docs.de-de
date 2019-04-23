---
title: Migrieren von .NET-Remoteanwendungen nach WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 4040fb0ac223f91705a49b733f6a1f42d144068e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091115"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="1adf2-102">Migrieren von .NET-Remoteanwendungen nach WCF</span><span class="sxs-lookup"><span data-stu-id="1adf2-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="1adf2-103">**Dieses Thema bezieht sich auf eine veraltete Technologie, die zum Zwecke der Abwärtskompatibilität mit vorhandenen Anwendungen beibehalten wird und nicht für die neue Entwicklung empfohlen wird. Verteilte Anwendungen sollten jetzt mithilfe von WCF entwickelt werden.**</span><span class="sxs-lookup"><span data-stu-id="1adf2-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="1adf2-104">Es gibt zwei Möglichkeiten von WCF mit vorhandenen .NET Remoting-Anwendungen nutzen: Integration und Migration.</span><span class="sxs-lookup"><span data-stu-id="1adf2-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="1adf2-105">Integration können Sie .NET Remoting 2.0 "und" WCF parallel ausgeführt wird, können Sie dieselben Geschäftsobjekte über beide Technologien gleichzeitig verfügbar zu machen ohne den vorhandenen .NET Remoting 2.0-Code ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="1adf2-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="1adf2-106">Voraussetzung der Integration ist, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1adf2-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="1adf2-107">Wenn Sie WCF-Features nutzen möchten, und netzwerkkompatibilität mit Remoting 2.0-Systemen ist nicht erforderlich, können Sie Ihre gesamten Dienst zu WCF migrieren.</span><span class="sxs-lookup"><span data-stu-id="1adf2-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="1adf2-108">Migration von .NET Remoting 2.0 nach WCF erfordert Änderungen am-Schnittstelle des Remoteobjekts und ihre Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1adf2-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="1adf2-109">Beide der folgenden Themen finden Sie im [von Remoting zu Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span><span class="sxs-lookup"><span data-stu-id="1adf2-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adf2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1adf2-110">See also</span></span>

- [<span data-ttu-id="1adf2-111">Konzeptionelle Übersicht</span><span class="sxs-lookup"><span data-stu-id="1adf2-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
