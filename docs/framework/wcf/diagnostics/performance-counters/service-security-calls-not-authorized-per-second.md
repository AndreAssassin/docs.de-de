---
title: 'Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: 523e5182ca661e170e5cba01d5221b5c38251959
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773361"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="7459b-102">Dienst: Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7459b-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="7459b-103">Indikatorname: Nicht autorisierte Sicherheitsaufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="7459b-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="7459b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7459b-104">Description</span></span>  
 <span data-ttu-id="7459b-105">Anzahl der eingehenden Nachrichten in einer Sekunde, die von einem gültigen Benutzer stammen und ordnungsgemäß geschützt sind, wobei der Benutzer allerdings nicht für die Durchführung spezifischer Aufgaben autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="7459b-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="7459b-106">Dieser Indikator wird erhöht, wenn die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7459b-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="7459b-107">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="7459b-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7459b-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="7459b-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
