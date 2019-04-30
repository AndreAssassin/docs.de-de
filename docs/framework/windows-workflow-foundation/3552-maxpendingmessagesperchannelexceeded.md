---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945937"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 - MaxPendingMessagesPerChannelExceeded
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3552|  
|Schlüsselwörter|Kontingent, WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass die Drosselungsgrenze 'MaxPendingMessagesPerChannel' erreicht wurde.  
  
## <a name="message"></a>Meldung  
 Die drosselungsgrenze ' maxpendingmessagesperchannel ' von '%1' wurde erreicht. Passen Sie die MaxPendingMessagesPerChannel-Eigenschaft von BufferedReceiveServiceBehavior an, um diese Grenze zu erhöhen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Limit|xs:string|Die Drosselungsgrenze 'MaxPendingMessagesPerChannel'.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
