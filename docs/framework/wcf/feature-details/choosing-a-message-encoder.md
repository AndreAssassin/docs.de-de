---
title: Auswählen eines Nachrichtenencoders
ms.date: 03/30/2017
ms.assetid: 2204d82d-d962-4922-a79e-c9a231604f19
ms.openlocfilehash: d93d7039d034262cd47edd437d5d7d8d63890f02
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635774"
---
# <a name="choose-a-message-encoder"></a>Wählen Sie einen Message Encoder

In diesem Artikel werden die Kriterien für die Auswahl der Nachrichtenencoder erläutert, die in Windows Communication Foundation (WCF) enthalten sind: Binär-, Text- und Nachrichtenübertragungsoptimierungsmechanismus (MTOM).  
  
 In WCF geben Sie an, wie Daten über ein Netzwerk zwischen Endpunkten mithilfe einer *Bindung*übertragen werden sollen, die aus einer Abfolge von *Bindungselementen*besteht. Ein Nachrichtenencoder wird von einem Nachrichtencodierungs-Bindungselement im Bindungsstapel dargestellt. Eine Bindung enthält optionale Protokollbindungselemente, wie ein Sicherheitsbindungselement oder ein zuverlässiges Nachrichtenbindungselement, ein erforderliches Nachrichtencodierungs-Bindungselement und ein erforderliches Transportbindungselement.  
  
 Das Nachrichtencodierungs-Bindungselement befindet sich unter den optionalen Protokollbindungselementen und über dem erforderlichen Transportbindungselement. Auf der ausgehenden Seite serialisiert ein Nachrichtenencoder die ausgehende <xref:System.ServiceModel.Channels.Message> und übergibt sie an den Transport. Auf der eingehenden Seite ruft ein Nachrichtenencoder die serialisierte Form einer <xref:System.ServiceModel.Channels.Message> aus dem Transport ab und übergibt sie an die höhere Protokollschicht, falls vorhanden, oder andernfalls an die Anwendung.  
  
 Wenn Sie eine Verbindung mit einem zuvor vorhandenen Client oder Server herstellen, haben Sie eventuell keine Wahl, ob Sie eine bestimmte Nachrichtencodierung verwenden möchten, da Sie Ihre Nachrichten auf eine Weise codieren müssen, die von der anderen Seite erwartet wird. Wenn Sie jedoch einen WCF-Dienst schreiben, können Sie den Dienst über mehrere Endpunkte verfügbar machen, die jeweils eine andere Nachrichtencodierung verwenden. So können Clients die beste Codierung für die Kommunikation mit Ihrem Dienst über den am besten geeigneten Endpunkt auswählen. Außerdem verfügen Sie dann über die Flexibilität, die für die Clients am besten geeignete Codierung auszuwählen. Die Verwendung von mehreren Endpunkten ermöglicht Ihnen, die Vorteile anderer Nachrichtencodierungen mit anderen Bindungselementen zu kombinieren.  
  
## <a name="system-provided-encoders"></a>Vom System bereitgestellte Encoder  
 WCF enthält drei Nachrichtengeber, die durch die folgenden drei Klassen dargestellt werden:  
  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>, der Textnachrichtenencoder, unterstützt sowohl reine XML-Codierung als auch SOAP-Codierung. Der reine XML-Codierungsmodus des Textnachrichtenencoders wird als "Plain Old XML" (POX) bezeichnet, um ihn von der textbasierten SOAP-Codierung zu unterscheiden. Um POX zu aktivieren, legen Sie die <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement.MessageVersion%2A>-Eigenschaft auf <xref:System.ServiceModel.Channels.MessageVersion.None%2A> fest. Verwenden Sie den Textnachrichtengeber, um mit Nicht-WCF-Endpunkten zusammenzuarbeiten.  
  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>, der binäre Nachrichtengeber, verwendet ein kompaktes Binärformat und ist für die WCF-zu-WCF-Kommunikation optimiert und daher nicht interoperabel. Dies ist auch der leistungsstärkste Encoder aller Encoder, die WCF bereitstellt.  
  
- Das <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>-Bindungselement gibt die Zeichencodierung und die für MTOM verwendete Nachrichtenversionsverwaltung an. MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten. Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu schaffen. Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung. In Bezug auf die Effizienz, unter den Encodern, die WCF bereitstellt, ist MTOM zwischen Text (der langsamste) und binär (der schnellste).  
  
## <a name="how-to-choose-a-message-encoder"></a>So wählen Sie einen Nachrichtenencoder aus  
 In der folgenden Tabelle werden allgemeine Faktoren beschrieben, die bei der Auswahl eines Nachrichtenencoders berücksichtigt werden. Priorisieren Sie die Faktoren, die für Ihre Anwendung wichtig sind, und wählen Sie dann die Nachrichtenencoder aus, die mit diesen Faktoren am besten funktionieren. Berücksichtigen Sie alle weiteren, in dieser Tabelle nicht aufgelisteten Faktoren sowie alle benutzerdefinierten Encoder, die eventuell für Ihre Anwendung erforderlich sind.  
  
|Faktor|BESCHREIBUNG|Encoder, die diesen Faktor unterstützen|  
|------------|-----------------|---------------------------------------|  
|Unterstützte Zeichensätze|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> unterstützen nur die UTF8- und UTF16-Unicode-Codierungen (*Big-Endian* und *Little-Endian).* Sind andere Codierungen erforderlich (beispielsweise UTF7 oder ASCII), muss ein benutzerdefinierter Encoder verwendet werden. Ein benutzerdefinierter Beispielgeber finden Sie unter [Benutzerdefinierter Nachrichtenencoder](https://docs.microsoft.com/dotnet/framework/wcf/samples/custom-message-encoder-custom-text-encoder).|Text|  
|Inspektion|Inspektion ist die Fähigkeit, Nachrichten während der Übertragung zu untersuchen. Textcodierungem, entweder mit oder ohne die Verwendung von SOAP, ermöglichen die Inspektion und Analyse von Nachrichten mit vielen Anwendungen, ohne spezielle Tools zu verwenden. Die Verwendung der Übertragungssicherheit auf Nachrichten- oder Transportebene wirkt sich auf Ihre Fähigkeit aus, Nachrichten zu überprüfen. Vertraulichkeit schützt eine Nachricht davor, untersucht zu werden, und Integrität schützt eine Nachricht davor, geändert zu werden.|Text|  
|Zuverlässigkeit|Zuverlässigkeit ist die Widerstandsfähigkeit eines Encoders gegen Übertragungsfehler. Zuverlässigkeit kann auch auf Nachrichten-, Transport- oder Anwendungsebene bereitgestellt werden. Alle Standard-WCF-Encoder gehen davon aus, dass eine andere Ebene für Zuverlässigkeit sorgt. Der Encoder hat wenige Möglichkeiten, nach einem Übertragungsfehler eine Wiederherstellung durchzuführen.|Keine|  
|Einfachheit|Einfachheit stellt die Leichtigkeit dar, mit der Sie Encoder und Decoder für eine Codierungsspezifikation erstellen können. Textcodierungen sind besonders vorteilhaft für die Einfachheit. Die POX-Textcodierung hat den zusätzlichen Vorteil, dass keine Unterstützung der SOAP-Verarbeitung erforderlich ist.|Text (POX)|  
|Größe|Die Codierung bestimmt den Mehraufwand für den Inhalt. Die Größe der codierten Nachrichten bezieht sich direkt auf den maximalen Durchsatz von Dienstvorgängen. Binäre Codierungen sind im Allgemeinen kompakter als Textcodierungen. Wenn die Nachrichtengröße ein Maximum erreicht hat, sollten Sie auch eine Komprimierung des Nachrichteninhalts während der Codierung in Erwägung ziehen. Durch die Komprimierung entstehen jedoch höhere Verarbeitungskosten für den Absender und den Empfänger der Nachricht.|Binary|  
|Streaming|Streaming ermöglicht Anwendungen, mit der Verarbeitung einer Nachricht zu beginnen, bevor die ganze Nachricht angekommen ist. Wenn Sie das Streaming effektiv anwenden möchten, ist es erforderlich, dass die wichtigen Daten einer Nachricht am Anfang der Nachricht zur Verfügung stehen, sodass die empfangende Anwendung nicht warten muss, bis die Nachricht ankommt. Außerdem müssen Anwendungen, die eine Übertragung per Stream nutzen, die Daten in der Nachricht inkrementell organisieren, damit der Inhalt keine Weiterleitungsabhängigkeiten aufweist. In vielen Fällen müssen Sie einen Kompromiss schließen zwischen dem Streaminginhalt und der kleinstmöglichen Übertragungsgröße dieses Inhalts.|Keine|  
|Tool-Unterstützung von Drittanbietern|Unterstützungsbereiche für eine Codierung umfassen Entwicklung und Diagnose. Drittanbieter haben viel investiert in Bibliotheken und Toolkits zur Verarbeitung von Nachrichten, die im POX-Format codiert sind.|Text (POX)|  
|Interoperabilität|Dieser Faktor bezieht sich auf die Fähigkeit eines WCF-Encoders, mit Nicht-WCF-Diensten zusammenzuarbeiten.|Text<br /><br /> MTOM (teilweise)|  
  
Hinweis: Bei Verwendung des Binärencoders hat die IgnoreWhitespace-Einstellung keine Auswirkung, wenn ein XML-Reader erstellt wird.  Angenommen, in einem Dienstvorgang wird Folgendes ausgeführt:  

```csharp
public void OperationContract(XElement input)
{
    Console.WriteLine("{0}", input.Value);
    int counter = 0;
    var xreader = input.CreateReader();
    var reader = XmlReader.Create(xreader, new XmlReaderSettings() { IgnoreWhitespace = true });
    while (reader.Read())
    {
        counter++;
    }

    Console.WriteLine("Read {0} lines with reader", counter);
}
```  
  
Die IgnoreWhitespace-Einstellung wird ignoriert.  
  
## <a name="compression-and-the-binary-encoder"></a>Komprimierung und binärer Encoder

Ab WCF 4.5 bietet der binäre WCF-Encoder Komprimierungsunterstützung. Dies ermöglicht es Ihnen, den gzip/deflate-Algorithmus zum Senden komprimierter Nachrichten von einem WCF-Client zu senden und mit komprimierten Nachrichten von einem selbst gehosteten WCF-Dienst zu antworten. Diese Funktion ermöglicht die Komprimierung bei HTTP- und TCP-Transporten. Ein IIS-gehosteter WCF-Dienst kann immer durch Konfigurieren des IIS-Hostservers zum Senden von komprimierten Antworten befähigt werden. Der Komprimierungstyp wird mit der <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A?displayProperty=nameWithType>-Eigenschaft konfiguriert. Diese Eigenschaft wird auf einen der <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>-Enumerationswerte festgelegt:

- <xref:System.ServiceModel.Channels.CompressionFormat.Deflate>
- <xref:System.ServiceModel.Channels.CompressionFormat.GZip>
- <xref:System.ServiceModel.Channels.CompressionFormat.None>
  
Da diese Eigenschaft nur für das binaryMessageEncodingBindingElement verfügbar gemacht wird, müssen Sie eine benutzerdefinierte Bindung wie die folgende erstellen, um diese Funktion zu verwenden:

 ```xml
 <customBinding>
   <binding name="BinaryCompressionBinding">
     <binaryMessageEncoding compressionFormat ="GZip" />
     <httpTransport />
  </binding>
</customBinding>
 ```

Sowohl der Client als auch der Dienst müssen dem Senden und Empfangen komprimierter Nachrichten zustimmen, und daher muss die compressionFormat-Eigenschaft für das binaryMessageEncoding-Element sowohl auf Client als auch auf Dienst konfiguriert werden. Eine ProtocolException wird ausgelöst, wenn entweder der Dienst oder der Client nicht für die Komprimierung konfiguriert ist, die andere Seite jedoch. Die Aktivierung der Komprimierung sollte sorgfältig geprüft werden. Die Komprimierung ist vor allem dann nützlich, wenn die Netzwerkbandbreite beschränkt ist. Wenn die CPU der Engpass ist, mindert die Komprimierung den Durchsatz. Es müssen entsprechende Tests in einer simulierten Umgebung ausgeführt werden, um zu ermitteln, ob dies für die Anwendung Vorteile erbringt.  
  
## <a name="see-also"></a>Siehe auch

- [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)
