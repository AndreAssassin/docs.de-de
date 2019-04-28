---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 7221f19dd131dbd60ef1a61625633d54dfdbe85a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769758"
---
# <a name="webmessageencoding"></a>\<webMessageEncoding>
Aktiviert Klartext-XML, JavaScript Object Notation (JSON)-Nachrichtencodierungen und unformatierten binären Inhalt, die bei der Verwendung in einer Windows Communication Foundation-Bindung (WCF) gelesen und geschrieben werden sollen.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<webMessageEncoding>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`maxReadPoolSize`|Die Anzahl von Nachrichten, die gleichzeitig gelesen werden können, ohne neue Reader zuzuordnen. Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets. Der Standard ist 64 Reader für jeden der inneren Encoder (Text, JSON und "unformatiert").<br /><br /> Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg eingehender Nachrichten vorbereitet, da er Reader aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Reader erstellt werden.|  
|`maxWritePoolSize`|Die maximale Anzahl von Nachrichten, die gleichzeitig gesendet werden können, ohne neue Writer zuzuordnen. Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets. Der Standard ist 16 Writer für jeden der inneren Encoder (Text, JSON und "unformatiert").<br /><br /> Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg ausgehender Nachrichten vorbereitet, da er Writer aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Writer erstellt werden.|  
|`writeEncoding`|Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Gültige Werte sind:<br /><br /> -   UnicodeFffeTextEncoding: Unicode-bigEndian-Codierung.<br />-Utf16TextEncoding: Unicode-Codierung.<br />-   Utf8TextEncoding: 8-Bit-Codierung.<br /><br /> Der Standardwert ist Utf8TextEncoding. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Codieren wird eine Nachricht in eine Bytefolge transformiert. Beim Decodieren wird dieser Prozess umgekehrt. Diese Vorgänge erfordern die Angabe einer Zeichencodierung.  
  
 Dazu delegiert das `webMessageEncoding`-Element Vorgänge an eine Reihe innerer Encoder, um die Klartext-XML und JSON-Codierungen sowie die unformatierten binären Daten zu verarbeiten. Diese Delegierung wird von einem zusammengesetzten Nachrichtenencoder durchgeführt.  
  
 Dieses Bindungselement und die zusammengesetzten Encoder werden zur Steuerung der Codierung in Szenarien eingesetzt, in denen keine SOAP-Nachrichten vom `webHttpBinding`-Element verwendet werden. Zu den Szenarien gehören u.&amp;#160;a. "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) And Atom Syndication sowie Asynchronous JavaScript And XML (AJAX). Der zusammengesetzte Nachrichtenencoder unterstützt SOAP oder WS-Addressing nicht.  
  
 Das Bindungselement kann mit dem `writeEncoding`-Attribut mit einer Schreibzeichencodierung konfiguriert werden. Der bereitgestellte <xref:System.Text.Encoding>-Wert gibt das Verhalten beim Schreiben für die JSON- und Text-XML-Fälle an. Beim Lesen wird jede gültige Nachrichtencodierung und Textcodierung interpretiert.  
  
 `maxReadPoolSize` und `maxWritePoolSize` können auch zum Festlegen der maximalen Anzahl an jeweils zuzuweisenden Readern und Writern verwendet werden. Standardmäßig werden 64 Reader und 16 Writer zugeordnet.  
  
 Standardkomplexitätseinschränkungen werden auch festlegen, über die [ \<ReaderQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) Element zum Schutz vor einer Klasse von Denial-of-Service (DOS)-Angriffe, die versuchen, die meldungskomplexität zum Binden von Endpunkt-Verarbeitung verwenden verwenden Ressourcen zu.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Nachrichtencodierung](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
