---
title: Entwickeln und Bereitstellen von WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: a3eaea7218b3226fde43aa76bbafe602fc198947
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329322"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Entwickeln und Bereitstellen von WCF Data Services

Dieses Thema enthält Informationen zum Entwickeln und Bereitstellen von WCF Data Services. Weitere grundlegende Informationen zu WCF Data Services, finden Sie unter [Einstieg](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) und [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Entwickeln von WCF Data Services

Wenn Sie WCF Data Services verwenden, um einen Datendienst erstellen, unterstützt die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], müssen Sie die folgenden grundlegenden Aufgaben ausführen, während der Entwicklung:

1. **Definieren des Datenmodells**

     WCF Data Services unterstützt eine Vielzahl von datendienstanbietern, die Ihnen ermöglichen, ein Datenmodell basierend auf Daten aus einer Vielzahl von Datenquellen, angefangen bei relationalen Datenbanken zu spät gebundener Datentypen zu definieren. Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

2. **Erstellen des Datendiensts**

     Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3. **Konfigurieren des Datendiensts**

     In der Standardeinstellung deaktiviert WCF Data Services den Zugriff auf Ressourcen, die von einem Entitätscontainer verfügbar gemacht werden. Die <xref:System.Data.Services.DataServiceConfiguration> -Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienstvorgänge, das Angeben der unterstützten Version von OData und definieren anderer dienstweiter Verhalten, wie das batchverarbeitungsverhalten oder die maximale Anzahl von Entitäten, die zurückgegeben werden kann. in einem einzelnen antwortfeed. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Dieses Thema behandelt in erster Linie die Entwicklung und Bereitstellung von Datendiensten mithilfe von Visual Studio. Informationen über die Flexibilität, die Ihnen von WCF Data Services für das Verfügbarmachen der Daten als OData-Feeds, finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Wählen Sie einen Development Webentwicklungsserver

Bei der Entwicklung eines WCF Data Service als ein [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Anwendung oder [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Website mithilfe von Visual Studio 2015, Sie haben die Wahl der Webserver auf dem den Datendienst während der Entwicklung ausgeführt. Die folgenden Web-Server integrieren von Visual Studio zu testen und Debuggen der Datendienste auf dem lokalen Computer zu vereinfachen.

1. **Lokaler IIS-Server**

     Wenn Sie einen Datendienst erstellen, bei dem es sich um eine unter Internetinformationsdienste (IIS) ausgeführte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung oder [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Website handelt, sollten Sie den Datendienst mit IIS auf dem lokalen Computer entwickeln und testen. Die Ausführung des Datendiensts unter IIS erleichtert die Ablaufverfolgung von HTTP-Anforderungen während des Debuggens. Zudem können Sie so vorab die Rechte bestimmen, die IIS für den Zugriff auf Dateien, Datenbanken und andere für den Datendienst erforderliche Ressourcen erfordert. Führen Sie den Datendienst unter IIS müssen Sie stellt sicher, dass sowohl IIS als auch Windows Communication Foundation (WCF) installiert und ordnungsgemäß konfiguriert sind, und gewähren Sie Zugriff auf IIS-Konten in das Dateisystem und Datenbanken. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln Sie einen WCF-Datendienst unter IIS ausgeführte](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Sie müssen Visual Studio mit Administratorrechten zum Aktivieren der Entwicklungsumgebung so konfigurieren Sie die lokalen IIS-Server ausführen.

2. **Visual Studio Development Server**

     Visual Studio enthält einen integrierten Webserver, der Visual Studio Development Server, dies ist der Standardwebserver für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekte. Dieser Webserver dient dazu, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekte während der Entwicklung auf dem lokalen Computer auszuführen. Die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) zeigt, wie Sie einen Datendienst erstellen, die in Visual Studio Development Server ausgeführt wird.

     Sie sollten die folgenden Einschränkungen bewusst sein, bei Verwendung von Visual Studio Development Server, zum Entwickeln eines Datendiensts verwenden:

    -   Auf diesen Server kann nur auf dem lokalen Computer zugegriffen werden.

    -   Dieser Server lauscht an `localhost` und an einem bestimmten Anschluss auf Nachrichten, nicht an Anschluss 80, dem Standardanschluss für HTTP-Nachrichten. Weitere Informationen finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    -   Dieser Server führt den Datendienst im Kontext Ihres aktuellen Benutzerkontos aus. Z. B. Wenn Sie als Benutzer mit Administratorrechten ausführen, haben in der Visual Studio Development Server ausgeführter Datendienst Administratorrechte. Dies kann dazu führen, dass der Datendienst auf Ressourcen zugreifen kann, für die er bei der Bereitstellung auf einem IIS-Server keine Zugriffsrechte besitzt.

    -   Die zusätzlichen Funktionen von IIS sind auf diesem Server nicht verfügbar (z. B. die Authentifizierung).

    -   Dieser Server kann nicht die aufgeteilte HTTP-Streams, verarbeiten die gesendet werden standardmäßig von der WCF Data Services-Client sein, umfangreiche binäre Daten aus dem Datendienst den Zugriff auf. Weitere Informationen finden Sie unter [Streaminganbieter](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).

    -   Dieser Server verfügt über Probleme bei der Verarbeitung des Punkts (`.`) Zeichen in einer URL, obwohl dieses Zeichen in den Schlüsselwerten von WCF Data Services unterstützt wird.

    > [!TIP]
    > Auch wenn Sie Visual Studio Development Server verwenden können, um Ihre Datendienste während der Entwicklung zu testen, sollten Sie sie nach der Bereitstellung auf einem Webserver, auf der IIS ausgeführt wird erneut testen.

3. **Microsoft Azure-Entwicklungsumgebung**

     Windows Azure Tools für Visual Studio enthält einen integrierten Satz von Tools zum Entwickeln von Windows Azure-Dienste in Visual Studio. Mit diesen Tools können Sie einen Datendienst entwickeln, der unter Windows Azure bereitgestellt werden kann, und den Datendienst vor der Bereitstellung auf dem lokalen Computer testen. Verwenden Sie diese Tools, wenn Visual Studio zum Entwickeln eines Datendiensts, das auf der Windows Azure-Plattform ausgeführt wird. Sie können die Windows Azure Tools für Visual Studio von der [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Weitere Informationen zur Entwicklung eines Datendiensts, der in Windows Azure ausgeführt wird, finden Sie im Beitrag [Bereitstellen von einem OData-Service in Windows Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="development-tips"></a>Tipps für die Entwicklung

Beachten Sie beim Entwickeln eines Datendiensts die folgenden Hinweise:

-   Bestimmen Sie die Sicherheitsanforderungen des Datendiensts, wenn Sie vorhaben, Benutzer zu authentifizieren oder den Zugriff für bestimmte Benutzer einzuschränken. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

-   Ein HTTP-Überprüfungsprogramm kann beim Debuggen eines Datendiensts hilfreich sein, da es Ihnen die Möglichkeit bietet, den Inhalt von Anforderungs- und Antwortnachrichten zu überprüfen. Zum Überprüfen von HTTP-Anforderungen an den Datendienst und HTTP-Antworten vom Datendienst kann eine beliebige Netzwerkpaketanalyse verwendet werden, die die Anzeige von Rohpaketen unterstützt.

-   Wenn Sie einen Datendienst zu debuggen, empfiehlt es sich um weitere Informationen zu einem Fehler vom Datendienst als während des normalen Betriebs zu erhalten. Sie können zusätzliche Fehlerinformationen vom Datendienst abrufen, indem Sie die <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> -Eigenschaft in der <xref:System.Data.Services.DataServiceConfiguration> auf `true` festlegen und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft des <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Attributs der Datendienstklasse auf `true`festlegen. Weitere Informationen finden Sie im Beitrag [Debuggen von WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=201868). Sie können auch die Ablaufverfolgung in WCF an, die in der HTTP-Messagingebene ausgelöste Ausnahmen anzeigen aktivieren. Weitere Informationen finden Sie unter [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).

-   Ein Datendienst wird in der Regel als entwickelt eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungsprojekt, aber Sie können außerdem erstellen Sie Data Service als ein [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Websiteprojekt in Visual Studio. Weitere Informationen zu den Unterschieden zwischen den zwei Projekttypen finden Sie unter [von Webanwendungsprojekten und Websiteprojekten in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

-   Wenn Sie einen Datendienst erstellen, mit der **neues Element hinzufügen** Dialogfeld in Visual Studio den Datendienst gehostet wird [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in IIS. Dies ( [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] und IIS) ist zwar der Standardhost für einen Datendienst, es werden jedoch auch andere Hostingoptionen unterstützt. Weitere Informationen finden Sie unter [Hosting des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Bereitstellen von WCF Data Services

Ein WCF Data Service bietet Flexibilität bei der Auswahl des Prozesses, von dem der Datendienst gehostet wird. Sie können Visual Studio verwenden, um einen Datendienst auf den folgenden Plattformen bereitstellen:

-   **IIS-gehosteter Webserver**

     Wenn ein Datendienst als [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekt entwickelt wird, kann es mit den standardmäßigen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Bereitstellungstechnologien auf einem IIS-Webserver bereitgestellt werden.  Visual Studio bietet die folgenden bereitstellungstechnologien für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], je nachdem, von der Art der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekt, das die den Datendienst hostet, die Sie bereitstellen.

    -   **Bereitstellungstechnologien für ASP.NET-Webanwendungen**

        -   [Vorgehensweise: Erstellen eines Webbereitstellungspakets in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

        -   [Vorgehensweise: Bereitstellen einer Web-Projekt mithilfe der One-Click-Veröffentlichung in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

    -   **Bereitstellungstechnologien für ASP.NET-Websites**

        -   [Vorgehensweise: Kopieren von Dateien der Website mit dem Tool zum Kopieren von Website](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

        -   [Vorgehensweise: Veröffentlichen von Websites](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

        -   [Exemplarische Vorgehensweise: Bereitstellen einer ASP.NET-Webanwendung mithilfe von XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Weitere Informationen zu den Optionen für die Bereitstellung einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung finden Sie unter [Web-Bereitstellungsübersicht für Visual Studio und ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Bevor Sie versuchen, den Datendienst unter IIS bereitzustellen, muss die Bereitstellung auf einem Webserver mit IIS getestet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Entwickeln Sie einen WCF-Datendienst unter IIS ausgeführte](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

-   **Microsoft Azure**

     Sie können einen Datendienst in Windows Azure bereitstellen, mithilfe von Windows Azure Tools für Visual Studio. Sie können die Windows Azure Tools für Visual Studio von der [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Weitere Informationen zum Bereitstellen eines Datendiensts mit Windows Azure finden Sie im Beitrag [Bereitstellen von einem OData-Service in Windows Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="deployment-considerations"></a>Überlegungen zur Bereitstellung

Beachten Sie beim Bereitstellen eines Datendiensts die folgenden Hinweise:

-   Wenn Sie einen Datendienst bereitstellen, der den [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] -Anbieter verwendet, um auf eine SQL Server-Datenbank zuzugreifen, müssen Sie möglicherweise auch Datenstrukturen, Daten oder beides mit der Datendienstbereitstellung weitergeben. Visual Studio kann automatisch Skripts (SQL-Dateien) klicken Sie hierzu in der Zieldatenbank erstellen und diese Skripts eingefügt werden können, in das Webbereitstellungspaket einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Anwendung. Weitere Informationen finden Sie unter [Vorgehensweise: Bereitstellen einer Datenbank mit einem Webanwendungsprojekt](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)). Für eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Website Sie hierzu mit der **Datenbankveröffentlichungs-Assistent** in Visual Studio. Weitere Informationen finden Sie unter [veröffentlichen eine SQL-Datenbank](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

-   Da WCF Data Services eine einfache WCF-Implementierung enthält, können Sie Windows Server AppFabric verwenden, um einen unter Windows Server unter IIS bereitgestellten Datendienst zu überwachen. Weitere Informationen zur Verwendung von Windows Server AppFabric zum Überwachen eines Datendiensts finden Sie im Beitrag [nachverfolgung von WCF Data Services mit Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=202005).

## <a name="see-also"></a>Siehe auch

- [Hosten des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
- [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
