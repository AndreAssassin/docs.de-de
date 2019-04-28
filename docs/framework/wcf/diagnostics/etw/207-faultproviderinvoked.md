---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 9f97e74e7685d57b487f456625826ee9cd8e1760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781913"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="ee0c3-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="ee0c3-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ee0c3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee0c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee0c3-104">ID</span><span class="sxs-lookup"><span data-stu-id="ee0c3-104">ID</span></span>|<span data-ttu-id="ee0c3-105">207</span><span class="sxs-lookup"><span data-stu-id="ee0c3-105">207</span></span>|  
|<span data-ttu-id="ee0c3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ee0c3-106">Keywords</span></span>|<span data-ttu-id="ee0c3-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ee0c3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ee0c3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ee0c3-108">Level</span></span>|<span data-ttu-id="ee0c3-109">Information</span><span class="sxs-lookup"><span data-stu-id="ee0c3-109">Information</span></span>|  
|<span data-ttu-id="ee0c3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ee0c3-110">Channel</span></span>|<span data-ttu-id="ee0c3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ee0c3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee0c3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee0c3-112">Description</span></span>  
 <span data-ttu-id="ee0c3-113">Dieses Ereignis wird ausgegeben, nachdem ein `FaultProvider` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee0c3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ee0c3-114">Message</span></span>  
 <span data-ttu-id="ee0c3-115">Der Verteiler hat einen FaultProvider vom Typ '%1' mit einer Ausnahme vom Typ '%2' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee0c3-116">Details</span><span class="sxs-lookup"><span data-stu-id="ee0c3-116">Details</span></span>  
  
|<span data-ttu-id="ee0c3-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ee0c3-117">Data Item Name</span></span>|<span data-ttu-id="ee0c3-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ee0c3-118">Data Item Type</span></span>|<span data-ttu-id="ee0c3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee0c3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee0c3-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ee0c3-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ee0c3-121">Der CLR-FullName des aufgerufenen `FaultProvider`-Typs.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="ee0c3-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ee0c3-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ee0c3-123">Der CLR-FullName der Ausnahme, die der `FaultProvider` verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="ee0c3-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="ee0c3-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="ee0c3-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ee0c3-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="ee0c3-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ee0c3-127">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ee0c3-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ee0c3-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ee0c3-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ee0c3-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
