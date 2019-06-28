---
title: Fehlerhafte Aufrufe pro Sekunde
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: aa8cd4c2d9f642b525b2b9ccb931c4f2101a5129
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421790"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="18e3d-102">Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="18e3d-102">Calls Failed Per Second</span></span>
<span data-ttu-id="18e3d-103">Indikatorname: Fehlerhafte Aufrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="18e3d-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="18e3d-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18e3d-104">Description</span></span>  
 <span data-ttu-id="18e3d-105">Anzahl von Aufrufen mit nicht behandelten Ausnahmen in diesem Vorgang innerhalb einer Sekunde.</span><span class="sxs-lookup"><span data-stu-id="18e3d-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="18e3d-106">Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="18e3d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="18e3d-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="18e3d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="18e3d-108">Dieser Indikator wird erhöht, jedes Mal, wenn eine nicht behandelte Ausnahme bei diesem Vorgang.</span><span class="sxs-lookup"><span data-stu-id="18e3d-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e3d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18e3d-109">See also</span></span>

- [<span data-ttu-id="18e3d-110">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="18e3d-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
