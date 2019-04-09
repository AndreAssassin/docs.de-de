---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 995ff9979096757225c9241e977f86f755955945
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158768"
---
# <a name="servicethrottling"></a>\<serviceThrottling>
Legt den Einschränkungsmechanismus eines WCF (Windows Communication Foundation)-Diensts fest.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceThrottling>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|maxConcurrentCalls|Eine positive ganze Zahl, die die Anzahl von Nachrichten begrenzt, die gegenwärtig auf einem <xref:System.ServiceModel.ServiceHost> verarbeitet werden. Aufrufe oberhalb des Limits werden in die Warteschlange gestellt. Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue. Der Standardwert ist 16 * Prozessoranzahl.|  
|maxConcurrentInstances|Eine positive ganze Zahl, die die Anzahl von <xref:System.ServiceModel.InstanceContext>-Objekten begrenzt , die gleichzeitig auf einem <xref:System.ServiceModel.ServiceHost> ausgeführt werden. Fordert das Erstellen zusätzlicher Instanzen an, die in eine Warteschlange eingereiht und abgeschlossen werden, wenn ein Slot unterhalb des Limits verfügbar wird. Der Standardwert entspricht der Summe von maxConcurrentSessions und MaxConcurrentCalls.|  
|maxConcurrentSessions|Eine positive ganze Zahl, die die Anzahl von Sitzungen begrenzt, die ein <xref:System.ServiceModel.ServiceHost>-Objekt akzeptieren kann.<br /><br /> Der Dienst akzeptiert Verbindungen über diesen Grenzwert hinaus, doch nur die Kanäle unter dem Grenzwert sind aktiv (Nachrichten werden von dem Kanal gelesen). Das Festlegen dieses Werts auf 0 (null) ist identisch mit dem Festlegen des Werts auf Int32.MaxValue. Der Standardwert ist 100 * Prozessoranzahl.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Mit der Einschränkung wird die Anzahl gleichzeitiger Aufrufe, Instanzen oder Sitzungen begrenzt, um eine übermäßige Ressourcenbeanspruchung zu verhindern.  
  
 Eine Ablaufverfolgung wird jedes Mal geschrieben, wenn der Wert von Attributen erreicht wird. Die erste Ablaufverfolgung wird als Warnung geschrieben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel beschränkt der Dienst die maximale Anzahl gleichzeitiger Aufrufe auf 2 und die maximale Anzahl gleichzeitiger Instanzen auf 10. Ein ausführliches Beispiel zum Ausführen dieses Beispiels finden Sie unter [Drosselung](../../../../../docs/framework/wcf/samples/throttling.md).  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
