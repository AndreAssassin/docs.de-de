---
title: Neues in Windows Communication Foundation 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
ms.openlocfilehash: eb506680f370e3571f1c38276d4e5d5890887a63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961706"
---
# <a name="whats-new-in-windows-communication-foundation-45"></a>Neues in Windows Communication Foundation 4.5

In diesem Thema erläutert die neuen auf Windows Communication Foundation (WCF), Version 4.5 Funktionen.

## <a name="wcf-simplification-features"></a>WCF-Vereinfachungsfunktionen

Es wurde viel unternommen, um die Entwicklung und Verwaltung von WCF 4.5-Anwendungen zu vereinfachen. Weitere Informationen finden Sie unter [WCF-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="task-based-async-support"></a>Aufgabenbasierte asynchrone Unterstützung

Durch Dienstverweis hinzufügen werden standardmäßig asynchrone Methoden für Dienstvorgänge generiert, die Tasks zurückgeben. Dies erfolgt sowohl für synchrone als auch für asynchrone Methoden. Auf diese Weise können die Dienstvorgänge mithilfe des neuen aufgabenbasierten asynchronen Programmiermodells asynchron aufgerufen werden. Wenn Sie die generierte Proxymethode aufrufen, erstellt WCF ein Taskobjekt, das den asynchronen Vorgang darstellt, und gibt diesen Task an Sie zurück. Die Aufgabe abgeschlossen wird, wenn der Vorgang abgeschlossen ist. Beim Implementieren eines asynchronen Vorgangs können Sie es als taskbasierten asynchronen Vorgang implementieren. Weitere Informationen finden Sie unter [synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).

### <a name="simplified-generated-configuration-files"></a>Vereinfachte generierte Konfigurationsdateien

Wenn Sie einen Dienstverweis in Visual Studio hinzufügen oder das SvcUtil.exe-Tool verwenden, wird eine Clientkonfigurationsdatei generiert. In früheren Versionen von WCF enthielten diese Konfigurationsdateien den Wert jeder Bindungseigenschaft, auch wenn deren Wert dem Standardwert entsprach. In WCF 4.5 enthalten die generierten Konfigurationsdateien nur die Bindungseigenschaften, die auf einen nicht standardmäßigen Wert festgelegt sind.

Weitere Informationen finden Sie unter [WCF-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md)

### <a name="contract-first-development"></a>Vertrag zuerst-Entwicklung

WCF unterstützt jetzt die Vertrag zuerst-Entwicklung. Die von svcutil.exe verfügt über einen/ServiceContract-Schalter zum Generieren von Dienst- und Datenverträgen aus einem WSDL-Dokument ermöglicht.

### <a name="add-service-reference-from-a-portable-subset-project"></a>Hinzufügen eines Dienstverweises aus einem Projekt für die portable Teilmenge

Projekte für portable Teilmengen ermöglichen es Programmierern von .NET-Assemblys, eine einzelne Quellstruktur zu verwalten und das System mit Unterstützung mehrerer .NET-Plattformen (Desktop, Silverlight, Windows Phone und XBOX) aufzubauen. Projekte für Portable Teilmengen verweisen nur auf .NET portable Bibliotheken, die eine .NET Framework-Assembly sind, die für jede beliebige .NET-Plattform verwendet werden kann. Die Entwicklererfahrung ist identisch mit dem Hinzufügen eines Dienstverweises innerhalb einer beliebigen anderen WCF-Clientanwendung. Weitere Informationen finden Sie unter [Hinzufügen eines Dienstverweises in einem Projekt der portablen Teilmenge](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).

### <a name="aspnet-compatibility-mode-default-changed"></a>Geänderter Standard für den ASP.NET-Kompatibilitätsmodus

WCF bietet einen ASP.NET-Kompatibilitätsmodus, der Entwicklern beim Schreiben von WCF-Diensten vollständigen Zugriff auf die Funktionen in der ASP.NET-HTTP-Pipeline gewährt. Um diesen Modus verwenden zu können, müssen Sie festlegen der `aspNetCompatibilityEnabled` Attribut auf "true", in der [ \<ServiceHostingEnvironment >](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) Abschnitt der Datei "Web.config". Außerdem muss die `RequirementsMode`-Eigenschaft für jeden Dienst in dieser appDomain für <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> festgelegt sein. Standardmäßig <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> ist nun so festgelegt <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>. Weitere Informationen finden Sie unter [Neuigkeiten in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) und [WCF-Dienste und ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).

### <a name="new-transport-default-values"></a>Neue Standardwerte für Transporte

Um die Konfiguration zu vereinfachen, wurden einige Standardwerte der Transporteigenschaft geändert. Weitere Informationen finden Sie unter [WCF-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> enthält konfigurierbare Kontingentwerte für XML-Wörterbuchreader, die den Arbeitsspeicher begrenzen, der beim Erstellen einer Nachricht von einem Encoder verwendet wird. Diese Kontingente sind konfigurierbar, allerdings wurden die Standardwerte geändert, um die Wahrscheinlichkeit zu verringern, dass sie von einem Entwickler explizit festgelegt werden müssen. Weitere Informationen finden Sie unter [WCF-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="wcf-configuration-validation"></a>WCF-Konfigurationsvalidierung

Im Rahmen des Buildvorgangs innerhalb von Visual Studio werden WCF-Konfigurationsdateien jetzt für die Attribute überprüft, die innerhalb des Projekts definiert sind. Eine Liste mit Validierungsfehlern oder Warnungen wird in Visual Studio angezeigt, wenn die Validierung fehlschlägt.

### <a name="xml-editor-tooltips"></a>XML-Editor-QuickInfos

Um neuen und bereits erfahrenen Entwicklern von WCF-Diensten die Konfiguration zu erleichtern, zeigt der XML-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.

## <a name="streaming-improvements"></a>Verbesserungen beim Streaming

Es wurde Unterstützung für echtes asynchrones Streaming hinzugefügt, bei dem die Senderseite keine Threads blockiert, wenn die Empfängerseite keine Nachrichten liest bzw. Nachrichten langsam liest. Dies erhöht die Skalierbarkeit. Die Einschränkung des Nachrichtenpuffers, die gilt, wenn ein Client eine gestreamte Nachricht an einen von IIS gehosteten WCF-Dienst sendet, wurde aufgehoben. Weitere Informationen finden Sie unter [WCF-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).

## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Einfacheres Verfügbarmachen eines Endpunkts über HTTPS mit IIS

Eine HTTPS-Protokollzuordnung wurde hinzugefügt, um das Verfügbarmachen eines Endpunkts über HTTPS zu vereinfachen. Um einen HTTPS-Endpunkt zu aktivieren, stellen Sie sicher, dass für die Website eine HTTPS-Bindung und ein SSL-Zertifikat konfiguriert wurden. Aktivieren Sie dann einfach HTTPS für das virtuelle Verzeichnis, von dem der Dienst gehostet wird. Wenn Metadaten für den Dienst aktiviert sind, werden sie ebenfalls über HTTPS verfügbar gemacht.

## <a name="generating-a-single-wsdl-document"></a>Generieren eines einzelnen WSDL-Dokuments

WSDL-Verarbeitungsstapel einiger Drittanbieter sind nicht in der Lage, WSDL-Dokumente zu verarbeiten, die über Abhängigkeiten mit anderen Dokumenten in Form von "xsd: import" verfügen. In WCF können Sie jetzt angeben, dass alle WSDL-Informationen in einem einzelnen Dokument zurückgegeben werden. Um anzufordern, fügen Sie ein einzelnes WSDL-Dokument "? SingleWSDL" an den URI an, wenn Metadaten vom Dienst angefordert.

## <a name="websocket-support"></a>WebSocket-Unterstützung

WebSockets ist eine Technologie, die die echte bidirektionale Kommunikation über die Ports 80 und 443 ermöglicht, wobei die Leistungsmerkmale denen von TCP ähneln. Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Bindungen hinzugefügt. <xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>. Weitere Informationen finden Sie unter folgenden Themen: [Vom System bereitgestellten Bindungen](../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="new-transport-default-values"></a>Neue Standardwerte für Transporte

Anhand der folgenden Tabelle erfahren Sie, welche Einstellungen geändert wurden und wo Sie zusätzliche Informationen finden.

|Eigenschaft|Ein|Neuer Standard|Weitere Informationen finden Sie unter|
|--------------|--------|-----------------|------------------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 Sekunden|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * Anzahl der Prozessoren|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * Anzahl der Prozessoren für den Transport<br /><br /> 4 \* Anzahl der Prozessoren für SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Konfigurieren des Net.TCP-Portfreigabediensts](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * Anzahl der Prozessoren|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 Sekunden|[Konfigurieren des Net.TCP-Portfreigabediensts](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)|

## <a name="xml-editor-tooltips"></a>XML-Editor-QuickInfos

Um neuen und bereits erfahrenen Entwicklern von WCF-Diensten die Konfiguration zu erleichtern, zeigt der XML-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.

## <a name="configuring-wcf-services-in-code"></a>Konfigurieren von WCF-Diensten in Code

Windows Communication Foundation (WCF) können Entwickler Dienste mithilfe von Konfigurationsdateien oder Code konfigurieren. Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde. Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich. Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein. Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht. WCF ermöglicht es auch die Konfiguration von Diensten in Code. In früheren Versionen von WCF (4.0 und früher) Konfigurieren von Diensten im Code in selbstgehosteten Szenarien einfach war die <xref:System.ServiceModel.ServiceHost> Klasse zulässig. Sie konfigurieren Endpunkte und Verhaltensweisen vor dem ServiceHost.Open aufgerufen wird. In webgehosteten Szenarien haben Sie jedoch keinen Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse. Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden. Ab .NET 4.5, bietet WCF eine einfachere Möglichkeit zum Konfigurieren Sie beide selbstgehostete und das Web gehostete Dienste im Code. Weitere Informationen finden Sie unter [Konfigurieren von WCF-Diensten im Code](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).

## <a name="channelfactory-caching"></a>ChannelFactory-Caching

WCF-Clientanwendungen verwenden die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um einen Kommunikationskanal mit einem WCF-Dienst zu erstellen. Die Erstellung von <xref:System.ServiceModel.ChannelFactory%601>-Instanzen verursacht einigen Mehraufwand, da sie die folgenden Vorgänge umfasst:

1. Erstellen der <xref:System.ServiceModel.Description.ContractDescription>-Struktur

2. Reflektieren aller erforderlichen CLR-Typen

3. Erstellen des Kanalstapels

4. Freigeben von Ressourcen

Um den Mehraufwand zu minimieren, kann WCF Kanalfactorys zwischenspeichern, wenn Sie einen WCF-Clientproxy verwenden. Weitere Informationen finden Sie unter [Kanalfactory und Zwischenspeichern](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).

## <a name="compression-and-the-binary-encoder"></a>Komprimierung und binärer Encoder

Ab WCF 4.5 bietet der binäre WCF-Encoder Komprimierungsunterstützung. Der Komprimierungstyp wird mit der <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>-Eigenschaft konfiguriert. Sowohl der Client als auch der Dienst müssen die <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>-Eigenschaft konfigurieren. Die Komprimierung unterstützt die HTTP-, HTTPS- und TCP-Protokolle. Wenn ein Client angibt, dass die Komprimierung verwendet werden soll, der Dienst aber keine Komprimierung unterstützt, wird eine Ausnahme über einen Protokollkonflikt ausgelöst. Weitere Informationen finden Sie unter [Auswählen eines Nachrichtenencoders](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)

## <a name="udp"></a>UDP

Unterstützung wurde für ein UDP-Transport ermöglicht es Entwicklern, Dienste zu schreiben, verwenden "fire and forget"-messaging. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.

## <a name="multiple-authentication-support"></a>Unterstützung mehrerer Authentifizierungen

Es werden jetzt mehrere Authentifizierungsmodi, so wie von IIS unterstützt, für einen einzelnen WCF-Endpunkt unterstützt, wenn der HTTP-Transport und die Transportsicherheit verwendet werden. IIS ermöglicht es Ihnen, mehrere Authentifizierungsmodi für ein virtuelles Verzeichnis zu aktivieren. Durch diese Funktion kann ein einzelner WCF-Endpunkt mehrere Authentifizierungsmodi unterstützen, die für das virtuelle Verzeichnis aktiviert sind, in dem der WCF-Dienst gehostet wird.

## <a name="idn-support"></a>IDN-Unterstützung

Unterstützung für WCF-Dienste mit IDNs (Internationalized Domain Names) wurde hinzugefügt. Weitere Informationen finden Sie unter [WCF und internationale Domänennamen](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).

## <a name="httpclient"></a>HttpClient

Eine neue Klasse mit dem Namen <xref:System.Net.Http.HttpClient> wurde hinzugefügt, um das Arbeiten mit HTTP-Anforderungen erheblich zu vereinfachen. Weitere Informationen finden Sie unter [apps vornehmen, soziale Netzwerke und eine Verbindung mit HTTP-Diensten](https://go.microsoft.com/fwlink/?LinkId=231886) und [HTTP-Client-Beispiels](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).

## <a name="configuration-intellisense"></a>IntelliSense-Konfiguration

Attributwerte in den Konfigurationsdateien für benutzerdefinierte Attribute, die im Projekt definiert sind, unterstützen jetzt IntelliSense, um das schnelle und präzise Arbeiten mit Konfigurationen zu erleichtern.

## <a name="configuration-tooltips"></a>QuickInfos zur Konfiguration

WCF-Elemente und Attribute QuickInfos im XML-Editor, um leichter und alle exakt den Zweck des Elements oder Attributs bestimmen.

## <a name="paste-data-as-classes"></a>Einfügen von Daten als Klassen

In einem WCF-Projekt können die in XML definierten Datentypen (die in einem Dienst verfügbar gemacht sind) direkt in eine Codepage eingefügt werden. Der XML-Typ wird als CLR-Typ eingefügt. Finden Sie unter [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md) Weitere Details.

## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost und Standardendpunkte

In Visual Studio 2010 wurde von WebServiceHost automatisch ein Standardendpunkt erstellt, unabhängig davon, ob ein Endpunkt explizit angegeben wurde oder nicht. In Visual Studio 2012 und höher erstellt WebServiceHost nur einen Standardendpunkt an, wenn keine Endpunkte explizit hinzugefügt werden. Wenn der Client den Standardendpunkt erwartet können explizit einen Endpunkt hinzufügen und den Client darauf verweisen. Alternativ können Sie WCF anweisen, zum früheren Verhalten zurückzukehren, indem Sie der Anwendungskonfigurationsdatei folgende Einstellung hinzufügen:

```xml
<appSettings>
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>
  </appSettings>
```

## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager

Diese von <xref:System.ServiceModel.Channels.IChannelFactory%601> verfügbar gemachte Schnittstelle vereinfacht die Verwendung von Cookies auf der Clientseite. Wenn AllowCookies für die Bindung auf True festgelegt ist, können Sie mit folgendem Code auf Cookies zugreifen:

```csharp
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();
System.Net.CookieContainer container = cookieManager.CookieContainer;
```

Anschließend können die Cookies unter Verwendung von <xref:System.Net.CookieContainer> abgerufen oder festgelegt werden. Wenn AllowCookies<xref:System.ServiceModel.OperationContext> auf False<xref:System.ServiceModel.OperationContext> festgelegt ist, können Sie die Cookies mit  manuell abrufen und in anderen Anforderungen unter Verwendung eines anderen  oder Meldungsinspektors senden. Die IHttpCookieContainerManager-Schnittstelle ermöglicht es Ihnen, einen Benutzer bei einem Dienst zu authentifizieren und das vom Dienst zurückgegebene Authentifizierungscookie zum Authentifizieren bei anderen Diensten zu verwenden.
