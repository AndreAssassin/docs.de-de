---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781822"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="08a5e-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="08a5e-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="08a5e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="08a5e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08a5e-104">ID</span><span class="sxs-lookup"><span data-stu-id="08a5e-104">ID</span></span>|<span data-ttu-id="08a5e-105">213</span><span class="sxs-lookup"><span data-stu-id="08a5e-105">213</span></span>|  
|<span data-ttu-id="08a5e-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="08a5e-106">Keywords</span></span>|<span data-ttu-id="08a5e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="08a5e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="08a5e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="08a5e-108">Level</span></span>|<span data-ttu-id="08a5e-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="08a5e-109">LogAlways</span></span>|  
|<span data-ttu-id="08a5e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="08a5e-110">Channel</span></span>|<span data-ttu-id="08a5e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="08a5e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="08a5e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08a5e-112">Description</span></span>  
 <span data-ttu-id="08a5e-113">Dieses Ereignis wird ausgegeben, wenn ein im Web gehosteter Diensthost gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="08a5e-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="08a5e-114">Dies kommt in der Regel vor, wenn der Dienst von einer Nachricht aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="08a5e-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="08a5e-115">Es kann auch vorkommen, wenn für den Dienst das automatische Starten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="08a5e-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="08a5e-116">Meldung</span><span class="sxs-lookup"><span data-stu-id="08a5e-116">Message</span></span>  
 <span data-ttu-id="08a5e-117">ServiceHost wurde gestartet: '%1'.</span><span class="sxs-lookup"><span data-stu-id="08a5e-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="08a5e-118">Details</span><span class="sxs-lookup"><span data-stu-id="08a5e-118">Details</span></span>  
  
|<span data-ttu-id="08a5e-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="08a5e-119">Data Item Name</span></span>|<span data-ttu-id="08a5e-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="08a5e-120">Data Item Type</span></span>|<span data-ttu-id="08a5e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08a5e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="08a5e-122">Service Type Name</span><span class="sxs-lookup"><span data-stu-id="08a5e-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="08a5e-123">Der CLR-FullName des Typs der Dienstimplementierung.</span><span class="sxs-lookup"><span data-stu-id="08a5e-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="08a5e-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="08a5e-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="08a5e-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="08a5e-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="08a5e-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="08a5e-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="08a5e-127">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="08a5e-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="08a5e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="08a5e-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="08a5e-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="08a5e-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
