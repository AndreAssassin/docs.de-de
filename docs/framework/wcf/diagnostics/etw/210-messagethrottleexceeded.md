---
title: 210 - MessageThrottleExceeded
ms.date: 03/30/2017
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
ms.openlocfilehash: 7ba5948b36642085ef44661b3d580e7f1c4102cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781880"
---
# <a name="210---messagethrottleexceeded"></a>210 - MessageThrottleExceeded
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|210|  
|Schlüsselwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn eine der drei Hauptdienstdrosselungen überschritten wurde. Beachten Sie, dass dieses Ereignis nur ausgegeben wird, wenn die Drosselungsgrenze anfänglich überschritten wird. Wenn die Drosselungsgrenze für gleichzeitige Aufrufe z. B. 10 beträgt, führt der elfte gleichzeitige Aufruf zu einem `MessageThrottleExceeded`-Ereignis. Der zwölfte Aufruf führt nicht zu einem weiteren Ereignis. Um einen unübersichtlichen Ereignistream zu vermeiden, führen Aktivitäten in der Nähe der Grenze nicht zu weiteren Ereignissen. Wenn in diesem Beispiel zwei Aufrufe abgeschlossen werden, sind neun gleichzeitige Aufrufe vorhanden. Falls dann zwei weitere Aufrufe eingehen, beträgt der aktuelle Wert wieder 11. Dies führt nicht zu einem weiteren Ereignis. Wenn der aktuelle WErt afu 70 Prozent der Drosselungsgrenze fällt, wird ein anderes Ereignis ausgegeben, das die Verlangsamung der Aktivität angibt. Darauffolgende Aktivitäten, die die Grenze überschreiten, führen zur Ausgabe eines weiteren `MessageThrottleExceeded`-Ereignisses. Falls die Anzahl gleichzeitiger Aufrufe in diesem Beispiel auf 7 fällt und dann wieder 11 erreicht, wird ein weiteres `MessageThrottleExceeded`-Ereignis ausgegeben.  
  
## <a name="message"></a>Meldung  
 Die '% 1'-Drosselungsgrenze von '%2' wurde erreicht.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Der Name der Drosselung, die überschritten wurde. Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.|  
|Limit|`xs:long`|Die momentan konfigurierte Grenze der Drosselung.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
