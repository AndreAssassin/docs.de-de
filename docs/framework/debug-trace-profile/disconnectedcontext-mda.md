---
title: disconnectedContext-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb42c04df6e02ff43421b7af6bf2d51b53aa3e69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181974"
---
# <a name="disconnectedcontext-mda"></a>disconnectedContext-MDA
Der `disconnectedContext`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn die CLR versucht, einen Übergang zu einem getrennten Apartment oder Kontext durchzuführen, während gerade eine Anforderung für ein COM-Objekt verarbeitet wird.  
  
## <a name="symptoms"></a>Symptome  
 Aufrufe, die auf einem [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) ausgeführt werden, werden an die zugrunde liegende COM-Komponente im aktuellen Apartment oder Kontext zugestellt, statt an den, in dem sie vorhanden sind. Dies kann zur Beschädigung oder zu Datenverlusten führen, wenn die COM-Komponente keine Multithread-Komponente ist, wie im Fall von Singlethread-Apartment-Komponenten (Single Thread Apartment, STA). Alternativ kann der Aufruf, wenn der RCW selbst ein Proxy ist, dazu führen, dass eine <xref:System.Runtime.InteropServices.COMException> mit einem HRESULT von RPC_E_WRONG_THREAD ausgelöst wird.  
  
## <a name="cause"></a>Ursache  
 Das OLE-Apartment oder der OLE-Kontext wurde heruntergefahren, als die CLR versucht hat, darin überzugehen. Dies wird meist durch STA-Apartments verursacht, die heruntergefahren werden, bevor alle COM-Komponenten, die im Besitz des Apartments sind, vollständig freigegeben wurden. Dies kann als Ergebnis eines expliziten Aufrufs aus Benutzercode von einem RCW auftreten, oder während die CLR selbst die COM-Komponente manipuliert, z. B. wenn die CLR die COM-Komponente freigibt, nachdem für den zugeordneten RCW eine Garbage Collection durchgeführt wurde.  
  
## <a name="resolution"></a>Auflösung  
 Um dieses Problem zu vermeiden, stellen Sie sicher, dass der Thread, der das STA besitzt, nicht beendet wird, bevor die Anwendung mit allen Objekten fertig ist, die in diesem Apartment vorhanden sind. Dasselbe gilt für Kontexte. Stellen Sie sicher, dass Kontexte nicht heruntergefahren werden, bevor die Anwendung mit allen COM-Komponenten vollständig fertig ist, die in diesem Kontext vorhanden sind.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Daten zu dem getrennten Kontext gemeldet.  
  
## <a name="output"></a>Output  
 Meldet das Kontextcookie des getrennten Apartments oder Kontexts.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
