---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 6fa68eed241edaea40b66c31240a4201e05779f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975343"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="32b54-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="32b54-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="32b54-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="32b54-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32b54-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="32b54-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="32b54-105">Methods</span></span>  
 <span data-ttu-id="32b54-106">Von der TcpConnectionPoolSettings-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="32b54-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="32b54-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="32b54-107">Properties</span></span>  
 <span data-ttu-id="32b54-108">Die TcpConnectionPoolSettings-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="32b54-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="32b54-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="32b54-109">GroupName</span></span>  
 <span data-ttu-id="32b54-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="32b54-110">Data type: string</span></span>  
  
 <span data-ttu-id="32b54-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32b54-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32b54-112">Der Gruppenname des vom Bindungselement verwendeten Verbindungspools.</span><span class="sxs-lookup"><span data-stu-id="32b54-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="32b54-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="32b54-113">IdleTimeout</span></span>  
 <span data-ttu-id="32b54-114">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="32b54-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="32b54-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32b54-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32b54-116">Die maximale Zeit, während der sich die Verbindung im Leerlauf befinden darf, bevor sie getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="32b54-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="32b54-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="32b54-117">LeaseTimeout</span></span>  
 <span data-ttu-id="32b54-118">Datentyp: Zeitpunkt (Datum und Uhrzeit)</span><span class="sxs-lookup"><span data-stu-id="32b54-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="32b54-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32b54-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32b54-120">Die maximale Zeit für die Ausführung eines Leasevorgangs, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="32b54-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="32b54-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="32b54-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="32b54-122">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="32b54-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="32b54-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="32b54-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="32b54-124">Die maximale Anzahl von ausgehenden Verbindungen pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="32b54-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32b54-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32b54-125">Requirements</span></span>  
  
|<span data-ttu-id="32b54-126">MOF</span><span class="sxs-lookup"><span data-stu-id="32b54-126">MOF</span></span>|<span data-ttu-id="32b54-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="32b54-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="32b54-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="32b54-128">Namespace</span></span>|<span data-ttu-id="32b54-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="32b54-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32b54-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32b54-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
