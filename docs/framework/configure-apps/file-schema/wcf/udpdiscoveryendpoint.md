---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: 180763404ee9070e9ed6e5476d4568a0a018dcb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203365"
---
# <a name="udpdiscoveryendpoint"></a>\<udpDiscoveryEndpoint>
Dieses Konfigurationselement definiert einen Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist. Dieser Endpunkt hat einen festen Vertrag und unterstützt zwei WS-Discovery-Protokollversionen. Außerdem weist er eine feste UDP-Bindung und eine Standardadresse gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.  
  
 \<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|discoveryMode|Eine Zeichenfolge, die den Modus des Suchprotokolls angibt. Gültige Werte sind "Adhoc" und "Managed". Im verwalteten Modus benötigt das Protokoll einen Suchproxy, der als Repository sichtbarer Dienste fungiert. Der Ad-hoc-Modus erfordert, dass das Protokoll den UDP-Multicastmechanismus verwendet, um verfügbare Dienste zu suchen. Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.|  
|discoveryVersion|Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt. Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005. Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.DiscoveryVersion>.|  
|maxResponseDelay|Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis bestimmte Meldungen gesendet werden, z. B. "Probe Match" oder "Resolve Match".<br /><br /> Wenn alle ProbeMatches zur gleichen Zeit gesendet werden, kann es zu einer Netzwerküberlastung kommen. Um zu verhindern, dass dieser Fall eintritt, werden ProbeMatches mit einer zufälligen Verzögerung zwischen den ProbeMatches gesendet. Die zufällige Verzögerung liegt im Bereich zwischen 0 und dem Wert, der von diesem Attribut festgelegt wurde. Wenn dieses Attribut auf 0 festgelegt wird, werden die ProbeMatches-Meldungen in einer engen Schleife ohne Verzögerung gesendet. Andernfalls werden die ProbeMatches-Meldungen mit einer zufällig festgelegten Verzögerung gesendet, sodass die Gesamtzeit zum Senden aller ProbeMatches-Meldungen den maxResponseDelay-Wert nicht überschreitet. Dieser Wert ist nur für Dienste relevant, er wird nicht von Clients verwendet.|  
|multicastAddress|Ein URI, der eine Multicastadresse angibt, die zum Senden und Empfangen der Ermittlungsnachrichten verwendet werden soll. Der Standardwert ist die Multicastadresse gemäß der Protokollspezifikation.|  
|`name`|Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt. Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<udpTransportSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|Eine Auflistung von Einstellungen, mit denen Sie die UDP-Transporteinstellungen für den UDP-Endpunkt konfigurieren können.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Dienst, der einen UDP-Multicasttransport auf Ermittlungsnachrichten überwacht.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
