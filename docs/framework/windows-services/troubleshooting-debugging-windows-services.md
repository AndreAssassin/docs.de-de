---
title: 'Problembehandlung: Debuggen von Windows-Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: 0552fc005a25e83065bb44e425770f9cef84f71b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082580"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="055bc-102">Problembehandlung: Debuggen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="055bc-102">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="055bc-103">Beim Debuggen einer Windows-Dienstanwendung interagiert der Dienst mit dem **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="055bc-103">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="055bc-104">Der **Service Manager** startet den Dienst durch Aufrufen der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und wartet dann 30 Sekunden auf die Rückgabe der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="055bc-104">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="055bc-105">Erfolgt in diesem Zeitraum keine Rückgabe durch die Methode, wird im Manager die Fehlermeldung angezeigt, dass der Dienst nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="055bc-105">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="055bc-106">Wenn Sie die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode wie unter [Vorgehensweise: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md) beschrieben debuggen, müssen Sie diese 30 Sekunden beachten.</span><span class="sxs-lookup"><span data-stu-id="055bc-106">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="055bc-107">Wenn Sie in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode einen Haltepunkt platzieren und der Durchlauf nicht innerhalb von 30 Sekunden abgeschlossen ist, wird der Dienst durch den Manager nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="055bc-107">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055bc-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="055bc-108">See also</span></span>

- [<span data-ttu-id="055bc-109">Vorgehensweise: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="055bc-109">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="055bc-110">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="055bc-110">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
