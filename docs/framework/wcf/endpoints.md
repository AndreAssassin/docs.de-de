---
title: Windows Communication Foundation-Endpunkte
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: b55abe937701f8708643efa2ea4cb62514b3521b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923187"
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="07c41-102">Windows Communication Foundation-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="07c41-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="07c41-103">Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="07c41-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="07c41-104">Endpunkte ermöglichen Clients den Zugriff auf die Funktionen, die ein WCF-Dienst bietet.</span><span class="sxs-lookup"><span data-stu-id="07c41-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="07c41-105">Eine Übersicht dazu, wie Sie einen Endpunkt zu erstellen, finden Sie unter [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="07c41-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="07c41-106">Jeder Endpunkt enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="07c41-106">Each endpoint contains:</span></span>  
  
- <span data-ttu-id="07c41-107">Eine Adresse, die angibt, wo der Endpunkt zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="07c41-107">An address that indicates where to find the endpoint.</span></span>  
  
- <span data-ttu-id="07c41-108">Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="07c41-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
- <span data-ttu-id="07c41-109">Ein Vertrag, der die verfügbaren Methoden identifiziert.</span><span class="sxs-lookup"><span data-stu-id="07c41-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="07c41-110">Beschreibungen, wie Sie diese einzelnen Teile eines Endpunkts angeben, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="07c41-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
- [<span data-ttu-id="07c41-111">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="07c41-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
- [<span data-ttu-id="07c41-112">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="07c41-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
- [<span data-ttu-id="07c41-113">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="07c41-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="07c41-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="07c41-114">In This Section</span></span>  
 [<span data-ttu-id="07c41-115">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="07c41-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="07c41-116">Beschreibt die Struktur eines Endpunkts und erläutert, wie Sie einen Endpunkt in einer Konfiguration oder im Code definieren und wie die Standardendpunkte, Bindungen und Verhalten von der Runtime bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="07c41-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="07c41-117">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="07c41-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="07c41-118">Beschreibt, wie die Kommunikation mit einem WCF-Dienst über Endpunkte erfolgt.</span><span class="sxs-lookup"><span data-stu-id="07c41-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="07c41-119">Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="07c41-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="07c41-120">Veranschaulicht, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="07c41-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="07c41-121">Vorgehensweise: Erstellen eines Dienstendpunkts im Code</span><span class="sxs-lookup"><span data-stu-id="07c41-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="07c41-122">Veranschaulicht, wie Sie einen Dienstendpunkt im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="07c41-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="07c41-123">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="07c41-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="07c41-124">Veranschaulicht, wie Sie Metadaten veröffentlichen, indem Sie Metadatenendpunkte in der Konfiguration und im Code veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="07c41-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="07c41-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="07c41-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="07c41-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="07c41-126">Related Sections</span></span>  
 [<span data-ttu-id="07c41-127">Grundlegender Programmierlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="07c41-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
