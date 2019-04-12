---
title: Streaminganbieter (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, binary data
- streaming data provider [WCF Data Services]
- WCF Data Services, streams
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
ms.openlocfilehash: 615443bee67d7ca69d25193404055b7299a58507
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517589"
---
# <a name="streaming-provider-wcf-data-services"></a>Streaminganbieter (WCF Data Services)
Ein Datendienst kann große BLOB-Daten (Binary Large Object) verfügbar machen. Diese Binärdaten können Video- und Audiostreams, Bilder, Dokumentdateien oder andere Typen binärer Medien darstellen. Wenn eine Entität im Datenmodell eine oder mehrere binäre Eigenschaften enthält, gibt der Datendienst diese als Base-64-codierte Binärdaten im Eintrag im Antwortfeed zurück. Da das Laden und Serialisieren von umfangreichen Binärdaten auf diese Weise die Leistung beeinträchtigen können die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] definiert einen Mechanismus zum Abrufen von Binärdaten unabhängig von der Entität, zu dem er gehört. Dies wird erreicht, indem die Binärdaten und die Entität in einen oder mehrere Datenströme getrennt werden.  
  
-   Medienressource – Binärdaten, die zu einer Entität gehören, z. B. ein Video, ein Audioelement, ein Bild oder ein anderer Typ von Medienressourcenstream.  
  
-   Medienlinkeintrag – eine Entität, die über einen Verweis auf einen zugehörigen Medienressourcenstream verfügt.  
  
 Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] definieren Sie einen binären Ressourcenstream durch das Implementieren eines Streamingdatenanbieters. Die streaminganbieterimplementierung Datendienst mit den als eine bestimmte Entität zugeordneten medienressourcenstream ein <xref:System.IO.Stream> Objekt. Diese Implementierung ermöglicht dem Datendienst, Medienressourcen über HTTP als binäre Datenströme eines angegebenen MIME-Typs zu akzeptieren und zurückzugeben.  
  
 Folgende Schritte sind erforderlich, um einen Datendienst zu konfigurieren, der das Streaming von Binärdaten unterstützt:  
  
1. Kennzeichnen Sie mindestens eine Entität im Datenmodell als Medienlinkeintrag. Diese Entitäten dürfen die als Datenstrom zu sendenden Binärdaten nicht enthalten. Alle binären Eigenschaften einer Entität werden im Eintrag stets als Base-64-codierte Binärdaten zurückgegeben.  
  
2. Implementieren Sie die T:System.Data.Services.Providers.IDataServiceStreamProvider-Schnittstelle.  
  
3. Definieren Sie einen Datendienst, der die <xref:System.IServiceProvider>-Schnittstelle implementiert. Der Datendienst verwendet die <xref:System.IServiceProvider.GetService%2A>-Implementierung, um auf die Implementierung des Streamingdatenanbieters zuzugreifen. Diese Methode gibt die entsprechende Streaminganbieterimplementierung zurück.  
  
4. Aktivieren Sie große Nachrichtendatenströme in der Konfiguration der Webanwendung.  
  
5. Aktivieren Sie den Zugriff auf binäre Ressourcen auf dem Server oder in einer Datenquelle.  
  
 In die Beispielen in diesem Thema basieren auf einer Stichprobe streamingfotodienst, das ausführlich im Beitrag erläutert wird [Data Services Streaming Provider Series: Implementing a Streaming Provider (Teil 1)](https://go.microsoft.com/fwlink/?LinkID=198989). Der Quellcode für diesen Beispieldienst ist auf die [Streaming Photo Data Service Sample Seite](https://go.microsoft.com/fwlink/?LinkID=198988) in der MSDN Code Gallery.  
  
## <a name="defining-a-media-link-entry-in-the-data-model"></a>Definieren eines Medienlinkeintrags im Datenmodell  
 Der Datenquellenanbieter bestimmt die Methode, mit der eine Entität im Datenmodell als Medienlinkeintrag definiert wird.  
  
 **Entity Framework-Anbieter**  
 Um anzugeben, dass eine Entität ein Medienlinkeintrag ist, fügen Sie der Entitätstypdefinition das `HasStream`-Attribut im konzeptionellen Modell hinzu, wie im folgenden Beispiel dargestellt:  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]  
  
 Sie müssen außerdem entweder der Entität oder dem Stamm der EDMX- oder CSDL-Datei, die das Datenmodell definiert, den Namespace `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` hinzufügen.  
  
 Ein Beispiel für ein Data-Dienst, verwendet der [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Anbieter und eine Medienressource verfügbar macht finden Sie im Beitrag [Data Services Streaming Provider Series: Implementing a Streaming Provider (Teil 1)](https://go.microsoft.com/fwlink/?LinkID=198989).  
  
 **Reflektionsanbieter**  
 Um anzugeben, dass eine Entität ein Medienlinkeintrag ist, fügen Sie der Klasse, die den Entitätstyp im Reflektionsanbieter definiert, <xref:System.Data.Services.Common.HasStreamAttribute> hinzu.  
  
 **Benutzerdefinierte Datendienstanbieter**  
 Wenn Sie benutzerdefinierte Dienstanbieter verwenden, implementieren Sie die <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle, um die Metadaten für den Datendienst zu definieren. Weitere Informationen finden Sie unter [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md). Sie geben an, dass ein binärer Ressourcenstream zu einem <xref:System.Data.Services.Providers.ResourceType> gehört, indem Sie die <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A>-Eigenschaft für den `true`, der den Entitätstyp (einen Medienlinkeintrag) darstellt, auf <xref:System.Data.Services.Providers.ResourceType> festlegen.  
  
## <a name="implementing-the-idataservicestreamprovider-interface"></a>Implementieren der IDataServiceStreamProvider-Schnittstelle  
 Um einen Datendienst zu erstellen, der binäre Datenströme unterstützt, müssen Sie die <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle implementieren. Diese Implementierung ermöglicht dem Datendienst, Binärdaten als Datenstrom an den Client zurückzugeben und Binärdaten als einen vom Client gesendeten Datenstrom zu nutzen. Der Datendienst erstellt immer dann eine Instanz dieser Schnittstelle, wenn er auf Binärdaten als Datenstrom zugreifen muss. Die <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle legt die folgenden Member fest:  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um die entsprechende Medienressource zu löschen, wenn ihr Medienlinkeintrag gelöscht wird. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, enthält diese Methode den Code, mit dem die dem angegebenen Medienlinkeintrag zugeordnete Medienressource gelöscht wird.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um eine Medienressource als Datenstrom zurückzugeben. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, enthält diese Methode den Code, der einen Datenstrom bereitstellt, der vom Datendienst zum Zurückgeben der dem bereitgestellten Medienlinkeintrag zugeordneten Medienressource verwendet wird.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|Diese Methode wird vom Datendienst aufgerufen, um den URI zurückzugeben, der zum Anfordern der Medienressource für den Medienlinkeintrag verwendet wird. Dieser Wert wird verwendet, um das `src`-Attribut im Inhaltselement des Medienlinkeintrags zu erstellen. Dieses wird verwendet, um den Datenstrom anzufordern. Wenn diese Methode `null` zurückgibt, bestimmt der Datendienst den URI automatisch. Verwenden Sie diese Methode, wenn Sie Clients mit direktem Zugriff auf binäre Daten ohne Verwendung des Streamanbieters bereitstellen müssen.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|Diese Methode wird vom Datendienst aufgerufen, um den Content-Type-Wert der Medienressource zurückzugeben, die dem angegebenen Medienlinkeintrag zugeordnet ist.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|Diese Methode wird vom Datendienst aufgerufen, um das eTag des Datenstroms zurückzugeben, das der angegebenen Entität zugeordnet ist. Diese Methode wird verwendet, wenn Sie Parallelität für die Binärdaten verwalten. Wenn diese Methode NULL zurückgibt, überwacht der Datendienst die Parallelität nicht.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um den Datenstrom abzurufen, der beim Empfangen des vom Client gesendeten Datenstroms verwendet wird. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, müssen Sie einen überschreibbaren Datenstrom zurückgeben, in den der Datendienst empfangene Datenstromdaten schreibt.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Gibt einen mit einem Namespace qualifizierten Typnamen zurück, der den Typ darstellt, den die Datendienstlaufzeit für den Medienlinkeintrag erstellen muss, der dem Datenstrom für die Medienressource zugeordnet ist, die eingefügt wird.|  
  
## <a name="creating-the-streaming-data-service"></a>Erstellen des Streamingdatendiensts  
 Damit die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Laufzeit auf die <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Implementierung zugreifen kann, muss der Datendienst, den Sie erstellen, auch die <xref:System.IServiceProvider>-Schnittstelle implementieren. Im folgenden Beispiel wird gezeigt, wie die <xref:System.IServiceProvider.GetService%2A>-Methode implementiert wird, um eine Instanz der `PhotoServiceStreamProvider`-Klasse zurückzugeben, die <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementiert.  
  
 [!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_service/cs/photodata.svc.cs#photoservicestreamingprovider)]
 [!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_service/vb/photodata.svc.vb#photoservicestreamingprovider)]  
  
 Allgemeine Informationen über das Erstellen eines Datendiensts finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
## <a name="enabling-large-binary-streams-in-the-hosting-environment"></a>Aktivieren von großen binären Datenströmen in der Hostumgebung  
 Wenn Sie einen Datendienst in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendung erstellen, wird Windows Communication Foundation (WCF) verwendet, um die HTTP-Protokollimplementierung bereitzustellen. Standardmäßig schränkt WCF die Größe von HTTP-Nachrichten auf nur 65 KB ein. Damit umfangreiche Binärdaten als Datenstrom zum und vom Datendienst gesendet werden können, müssen Sie auch die Webanwendung für die Verwendung großer Binärdateien und den Einsatz von Datenströmen für die Übertragung konfigurieren. Fügen Sie dazu Folgendes im `<configuration />`-Element der Datei Web.config der Anwendung hinzu:  

> [!NOTE]
>  Verwenden Sie eine <xref:System.ServiceModel.TransferMode.Streamed?displayProperty=nameWithType> Übertragungsmodus, um sicherzustellen, dass die Binärdaten im sowohl die Anforderungs-und Antwortnachrichten gestreamt und von WCF nicht gepuffert.  
  
 Weitere Informationen finden Sie unter [Nachrichtenübertragung per Stream](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md) und [Transportkontingente](../../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 Darüber hinaus wird die Größe von Anforderungen von Internetinformationsdienste (IIS) standardmäßig auf 4 MB begrenzt. Um Datenströme, die größer als 4 MB zu erhalten, wenn die Ausführung in IIS vom Datendienst zu aktivieren, müssen Sie auch Festlegen der `maxRequestLength` Attribut der [HttpRuntime-Element ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e1f13641(v=vs.100)) in die `<system.web />` Konfigurationsabschnitt als Im folgenden Beispiel gezeigt:  

## <a name="using-data-streams-in-a-client-application"></a>Verwenden von Datenströmen in einer Clientanwendung  
 Mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek können Sie diese verfügbar gemachten Ressourcen als binäre Datenströme auf dem Client abrufen und aktualisieren. Weitere Informationen finden Sie unter [arbeiten mit Binärdaten](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md).  
  
## <a name="considerations-for-working-with-a-streaming-provider"></a>Überlegungen zum Arbeiten mit einem Streaminganbieter  
 Folgende Aspekte sollten bei der Implementierung eines Streaminganbieters und beim Zugriff auf Medienressourcen von einem Datendienst aus berücksichtigt werden.  
  
-   MERGE-Anforderungen werden für Medienressourcen nicht unterstützt. Verwenden Sie eine PUT-Anforderung, um die Medienressource einer vorhandenen Entität zu ändern.  
  
-   Eine POST-Anforderung kann nicht verwendet werden, um einen neuen Medienlinkeintrag zu erstellen. Stattdessen müssen Sie eine POST-Anforderung absetzen, um eine neue Medienressource zu erstellen, und der Datendienst erstellt einen neuen Medienlinkeintrag mit Standardwerten. Diese neue Entität kann durch eine nachfolgende MERGE- oder PUT-Anforderung aktualisiert werden. Sie sollten außerdem in Betracht ziehen, die Entität zwischenzuspeichern und Aktualisierungen in der Funktion zum Entfernen vorzunehmen, z. B. das Festlegen des Eigenschaftswerts auf den Wert des Headers des Platzhalterfelds in der POST-Anforderung.  
  
-   Wenn eine POST-Anforderung empfangen wird, ruft der Datendienst <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> auf, um die Medienressource zu erstellen, bevor er <xref:System.Data.Services.IUpdatable.SaveChanges%2A> aufruft, um den Medienlinkeintrag zu erstellen.  
  
-   Eine Implementierung von <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> sollte kein <xref:System.IO.MemoryStream>-Objekt zurückgeben. Bei der Verwendung solcher Datenströme treten Speicherressourcenprobleme auf, wenn der Dienst sehr große Datenströme empfängt.  
  
-   Folgende Aspekte müssen berücksichtigt werden, wenn Medienressourcen in einer Datenbank gespeichert werden:  
  
    -   Eine binäre Eigenschaft, die eine Medienressource ist, sollte nicht im Datenmodell enthalten sein. Alle in einem Datenmodell zur Verfügung gestellten Eigenschaften werden im Eintrag in einem Antwortfeed zurückgegeben.  
  
    -   Um die Leistung bei einem großen binären Datenstrom zu verbessern, empfiehlt es sich, eine benutzerdefinierte Datenstromklasse zu erstellen, um Binärdaten in der Datenbank zu speichern. Diese Klasse wird von der <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>-Implementierung zurückgegeben und sendet die Binärdaten in Blöcken an die Datenbank. Für eine SQL Server-Datenbank empfehlen wir, dass Sie FILESTREAM zum Streamen von Daten in die Datenbank verwenden, wenn die Binärdaten größer als 1 MB sind.  
  
    -   Stellen Sie sicher, dass die Datenbank zum Speichern großer binärer Datenströme entworfen wurde, die vom Datendienst empfangen werden sollen.  
  
    -   Wenn ein Client eine POST-Anforderung sendet, um einen Medienlinkeintrag mit einer Medienressource in einer einzelnen Anforderung einzufügen, wird <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> aufgerufen, um den Datenstrom abzurufen, bevor der Datendienst die neue Entität in die Datenbank einfügt. Eine Streaminganbieterimplementierung muss in der Lage sein, mit diesem Verhalten des Datendiensts umzugehen. Sie können die Binärdaten mithilfe einer separaten Datentabelle speichern oder den Datenstrom in einer Datei speichern, bis die Entität in die Datenbank eingefügt wurde.  
  
-   Wenn Sie die Methode <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A> oder <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> implementieren, müssen Sie die eTag- und Content-Type-Werte verwenden, die als Methodenparameter angegeben werden. Legen Sie keine eTag- oder Content-Type-Header in der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Anbieterimplementierung fest.  
  
-   Standardmäßig sendet der Client große binäre Datenströme mithilfe einer segmentierten HTTP-Übertragungscodierung. Da die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server diese Art von Codierung nicht unterstützt, Sie können nicht diesen Webserver verwenden, um einen streamingdatendienst zu hosten, der große binäre Datenströme annehmen muss. Weitere Informationen zu [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).  
  
<a name="versioning"></a>   
## <a name="versioning-requirements"></a>Versionsanforderungen  
 Der Streaminganbieter hat die folgenden Anforderungen an die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokollversion:  
  
-   Der Streaminganbieter erfordert, dass der Datendienst Version 2.0 des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls und höhere Versionen unterstützt.  
  
 Weitere Informationen finden Sie unter [Datendienst-Versionskontrolle](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)
- [Arbeiten mit Binärdaten](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)
