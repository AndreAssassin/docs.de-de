---
title: Transporte in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933730"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="81e37-102">Transporte in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="81e37-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="81e37-103">Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels.</span><span class="sxs-lookup"><span data-stu-id="81e37-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="81e37-104">Hauptsächlich in Windows Communication Foundation (WCF) verwendeten Transportprotokolle sind HTTP, HTTPS, TCP und named Pipes.</span><span class="sxs-lookup"><span data-stu-id="81e37-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="81e37-105">Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="81e37-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="81e37-106">WCF schließt zusätzliche Transporte ein.</span><span class="sxs-lookup"><span data-stu-id="81e37-106">WCF includes additional transports.</span></span> <span data-ttu-id="81e37-107">Weitere Informationen zu Message Queuing (auch bekannt als MSMQ)-Transport, finden Sie unter [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="81e37-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="81e37-108">Weitere Informationen zu-Peer-zu-Peer-Transport, finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="81e37-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81e37-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81e37-109">In This Section</span></span>  
 [<span data-ttu-id="81e37-110">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="81e37-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="81e37-111">Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.</span><span class="sxs-lookup"><span data-stu-id="81e37-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="81e37-112">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="81e37-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="81e37-113">Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung-Bindungselements zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="81e37-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="81e37-114">Streamen der Nachrichtenübertragung</span><span class="sxs-lookup"><span data-stu-id="81e37-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="81e37-115">Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="81e37-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="81e37-116">Konfigurieren von HTTP und HTTPS</span><span class="sxs-lookup"><span data-stu-id="81e37-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="81e37-117">Beschreibt, wie HTTP- und HTTPS-Transportbindungselemente konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="81e37-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="81e37-118">Vorgehensweise: Ersetzen Sie die WCF URL-Reservierung durch eine eingeschränkte Reservierung</span><span class="sxs-lookup"><span data-stu-id="81e37-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="81e37-119">Beschreibt, wie Reservierungen für WCFURL eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="81e37-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="81e37-120">Transportkontingente</span><span class="sxs-lookup"><span data-stu-id="81e37-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="81e37-121">Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="81e37-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="81e37-122">Arbeiten mit NATs und Firewalls</span><span class="sxs-lookup"><span data-stu-id="81e37-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="81e37-123">Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT (Network Address Translation) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="81e37-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="81e37-124">Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="81e37-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="81e37-125">Beschreibt, wie die Net.TCP Port Sharing-Komponente von WCF verwenden.</span><span class="sxs-lookup"><span data-stu-id="81e37-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="81e37-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="81e37-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="81e37-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="81e37-127">Related Sections</span></span>  
 [<span data-ttu-id="81e37-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="81e37-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="81e37-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="81e37-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
