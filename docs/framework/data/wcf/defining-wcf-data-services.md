---
title: Definieren von WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: b9280936a16d50283c01120c9dc046e65a0a79ae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790875"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="eb1c0-102">Definieren von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="eb1c0-102">Defining WCF Data Services</span></span>

<span data-ttu-id="eb1c0-103">In diesem Abschnitt wird beschrieben, wie WCF Data Services erstellt und konfiguriert wird, um [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Daten als-Feed verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="eb1c0-104">Weitere Informationen zu den grundlegenden Schritten, die zum Erstellen eines Daten Dienstanbieter erforderlich sind, finden Sie unter verfügbar machen von [Daten als Dienst](exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb1c0-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb1c0-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eb1c0-105">In This Section</span></span>

 [<span data-ttu-id="eb1c0-106">Konfigurieren des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="eb1c0-106">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="eb1c0-107">Beschreibt die von WCF Data Services bereitgestellten Datendienst-Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="eb1c0-108">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="eb1c0-108">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="eb1c0-109">Beschreibt die Anbietermodelle zum Verfügbarmachen von Daten als Datendienst.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="eb1c0-110">Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="eb1c0-110">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="eb1c0-111">Beschreibt, wie Dienstvorgänge definiert werden, die Methoden auf dem Server verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="eb1c0-112">Anpassung von Feeds</span><span class="sxs-lookup"><span data-stu-id="eb1c0-112">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="eb1c0-113">Beschreibt das Erstellen einer Zuordnung zwischen Entitäten im Datenmodell, das vom Datendienstanbieter definiert wird, und den Elementen im Datenfeed.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="eb1c0-114">Interceptors</span><span class="sxs-lookup"><span data-stu-id="eb1c0-114">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="eb1c0-115">Beschreibt, wie Interceptormethoden definiert werden, um benutzerdefinierte Geschäftslogik für Anforderungen an den Datendienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="eb1c0-116">Entwickeln und Bereitstellen von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="eb1c0-116">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="eb1c0-117">Beschreibt, wie ein Datendienst mithilfe von Visual Studio entwickelt und bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="eb1c0-118">Sichern von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="eb1c0-118">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="eb1c0-119">Beschreibt die Authentifizierung und Autorisierung für den Datendienst sowie weitere Sicherheitsüberlegungen.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="eb1c0-120">Hosten des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="eb1c0-120">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="eb1c0-121">Beschreibt, wie ein Host für den Datendienst ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="eb1c0-122">Datendienst-Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="eb1c0-122">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="eb1c0-123">Beschreibt das Arbeiten mit verschiedenen Versionen von odata.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="eb1c0-124">Details der WCF Data Services-Protokollimplementierung</span><span class="sxs-lookup"><span data-stu-id="eb1c0-124">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="eb1c0-125">Beschreibt optionale Funktionen des odata-Protokolls, die derzeit nicht von WCF Data Services implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb1c0-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb1c0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb1c0-126">See also</span></span>

- [<span data-ttu-id="eb1c0-127">WCF Data Services-Clientbibliothek</span><span class="sxs-lookup"><span data-stu-id="eb1c0-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="eb1c0-128">Zugreifen auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="eb1c0-128">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="eb1c0-129">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="eb1c0-129">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
