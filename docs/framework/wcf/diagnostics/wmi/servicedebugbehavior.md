---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956961"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die ServiceDebugBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die ServiceDebugBehavior-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt an, ob verwaltete Ausnahmeinformationen in Details der SOAP-Fehler für Debugzwecke an die Clients zurückgegeben werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
