---
title: WCF-Suche
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768692"
---
# <a name="wcf-discovery"></a><span data-ttu-id="7f33d-102">WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="7f33d-102">WCF Discovery</span></span>
<span data-ttu-id="7f33d-103">Windows Communication Foundation (WCF) bietet Unterstützung dafür, dass Dienste erkennbar sind, zur Laufzeit auf interoperable Weise mithilfe des WS-Discovery-Protokolls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f33d-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="7f33d-104">WCF-Dienste können ihre Verfügbarkeit im Netzwerk mit einer Multicastnachricht oder für einen suchproxyserver ankündigen.</span><span class="sxs-lookup"><span data-stu-id="7f33d-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="7f33d-105">Clientanwendungen können ein Netzwerk oder einen Suchproxyserver durchsuchen, um Dienste zu ermitteln, die eine bestimmte Gruppe von Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7f33d-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="7f33d-106">Die Themen in diesem Abschnitt enthalten eine Übersicht, und das Programmiermodell für diese Funktion wird ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f33d-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f33d-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7f33d-107">In This Section</span></span>  
 [<span data-ttu-id="7f33d-108">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="7f33d-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="7f33d-109">Bietet eine Übersicht über WS-Discovery-Unterstützung, die von WCF bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7f33d-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="7f33d-110">Objektmodell der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="7f33d-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="7f33d-111">Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit der WS-Discovery-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="7f33d-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="7f33d-112">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und Client</span><span class="sxs-lookup"><span data-stu-id="7f33d-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="7f33d-113">Veranschaulicht, wie einen Windows Communication Foundation (WCF)-Dienst erkennbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="7f33d-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="7f33d-114">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="7f33d-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="7f33d-115">Beschreibt die Schritte, die erforderlich sind, um Folgendes zu implementieren: einen Suchproxy, einen erkennbaren Dienst, der sich beim Suchproxy registriert, und einen Client, der den Suchproxy zum Suchen nach dem erkennbaren Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f33d-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="7f33d-116">Versionskontrolle für die Ermittlung</span><span class="sxs-lookup"><span data-stu-id="7f33d-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="7f33d-117">Bietet eine kurze Übersicht über eine Prototypimplementierung einiger neuer Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="7f33d-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="7f33d-118">Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.</span><span class="sxs-lookup"><span data-stu-id="7f33d-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="7f33d-119">Konfigurieren der Ermittlung in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="7f33d-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="7f33d-120">Beschreibt, wie Sie die Suche in der Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f33d-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="7f33d-121">Verwenden des Ermittlungsclientkanals</span><span class="sxs-lookup"><span data-stu-id="7f33d-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="7f33d-122">Veranschaulicht, wie ein Discovery-Clientchannel zu verwenden, wenn eine WCF-Clientanwendung schreiben.</span><span class="sxs-lookup"><span data-stu-id="7f33d-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
