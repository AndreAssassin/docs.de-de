---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: b0a621da43402777cc620f1876bd968a72bb8c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973108"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="1f103-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="1f103-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="1f103-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="1f103-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f103-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f103-104">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1f103-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1f103-105">Methods</span></span>  
 <span data-ttu-id="1f103-106">Mit der ReliableSessionBindingElement-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="1f103-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1f103-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1f103-107">Properties</span></span>  
 <span data-ttu-id="1f103-108">Die ReliableSessionBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1f103-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="1f103-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="1f103-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="1f103-110">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="1f103-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="1f103-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-112">Das Zeitintervall, in dem ein Ziel wartet, bevor eine Bestätigung an die Nachrichtenquelle in zuverlässigen Kanälen gesendet wird, die von der Factory erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1f103-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="1f103-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="1f103-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="1f103-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="1f103-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f103-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-116">Ein boolescher Wert, der angibt, ob die Flusssteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1f103-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="1f103-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="1f103-117">InactivityTimeout</span></span>  
 <span data-ttu-id="1f103-118">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="1f103-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="1f103-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-120">Gibt die maximale Dauer an, die der Kanal dem anderen Kommunikationsteilnehmer für das ausbleibende Senden von Nachrichten zugesteht, bevor im Kanal ein Fehler ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1f103-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="1f103-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="1f103-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="1f103-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1f103-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f103-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-124">Die maximale Anzahl von Kanälen, die auf dem Listener akzeptiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1f103-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="1f103-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="1f103-125">MaxRetryCount</span></span>  
 <span data-ttu-id="1f103-126">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1f103-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f103-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-128">Maximale Anzahl der Versuche eines zuverlässigen Kanals, eine Nachricht, für die keine Bestätigung empfangen wurde, erneut zu übertragen (durch Aufrufen von `Send` im zugrunde liegenden Kanal).</span><span class="sxs-lookup"><span data-stu-id="1f103-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="1f103-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="1f103-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="1f103-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="1f103-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f103-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-132">Die maximale Übertragungsfenstergröße für die zuverlässige Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1f103-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="1f103-133">Geordnete</span><span class="sxs-lookup"><span data-stu-id="1f103-133">Ordered</span></span>  
 <span data-ttu-id="1f103-134">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="1f103-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f103-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-136">Ein boolescher Wert, der angibt, ob Nachrichten auf jeden Fall in der Reihenfolge ihres Versands eintreffen.</span><span class="sxs-lookup"><span data-stu-id="1f103-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="1f103-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="1f103-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="1f103-138">Datentyp: Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="1f103-138">Data type: integer</span></span>  
  
 <span data-ttu-id="1f103-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1f103-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f103-140">Eine ganze Zahl, die die in der zuverlässigen Sitzung verwendete WS-ReliableMessaging Protokollversion angibt.</span><span class="sxs-lookup"><span data-stu-id="1f103-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f103-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f103-141">Requirements</span></span>  
  
|<span data-ttu-id="1f103-142">MOF</span><span class="sxs-lookup"><span data-stu-id="1f103-142">MOF</span></span>|<span data-ttu-id="1f103-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1f103-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1f103-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="1f103-144">Namespace</span></span>|<span data-ttu-id="1f103-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1f103-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f103-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f103-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
