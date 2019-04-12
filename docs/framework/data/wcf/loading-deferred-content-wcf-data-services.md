---
title: Laden von verzögerten Inhalten (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 32f9b588-c832-44c4-a7e0-fcce635df59a
ms.openlocfilehash: ee7b0b40d74d908dc4f25372273f852662370df0
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59518005"
---
# <a name="loading-deferred-content-wcf-data-services"></a>Laden von verzögerten Inhalten (WCF Data Services)
Standardmäßig schränkt [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] die Datenmenge ein, die eine Abfrage zurückgibt. Sie können jedoch explizit weitere Daten aus dem Datendienst laden, einschließlich verknüpfter Entitäten, ausgelagerter Antwortdaten und binärer Datenströme, wenn sie benötigt werden. In diesem Thema wird beschrieben, wie dieser verzögerte Inhalt in die Anwendung geladen wird.  
  
## <a name="related-entities"></a>Verknüpfte Entitäten  
 Beim Ausführen einer Abfrage werden nur Entitäten in der behandelten Entitätenmenge zurückgegeben. Wenn beispielsweise eine Abfrage des Northwind-Datendiensts `Customers`-Entitäten zurückgibt, werden die verknüpften `Orders`-Entitäten standardmäßig nicht zurückgegeben, obwohl eine Beziehung zwischen `Customers` und `Orders` besteht. Außerdem müssen Sie, wenn Paging im Datendienst aktiviert ist, explizit nachfolgende Datenseiten aus dem Dienst laden. Es gibt zwei Möglichkeiten zum Laden verknüpfter Entitäten:  
  
-   **Eager Loading**: Sie können die `$expand` -Abfrageoption verwenden, um die anfordern, dass die Abfrage Entitäten zurückgibt, die durch eine Zuordnung für die Entität verknüpft sind, die die angeforderte Abfrage festlegen. Verwenden Sie die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceQuery%601>, um der Abfrage, die an den Datendienst gesendet werden soll, die `$expand`-Option hinzuzufügen. Sie können mehrere verknüpfte Entitätenmengen anfordern, indem Sie sie wie im folgenden Beispiel durch ein Komma trennen. Alle von der Abfrage angeforderten Entitäten werden in einer einzelnen Antwort zurückgegeben. Im folgenden Beispiel werden `Order_Details` und `Customers` zusammen mit der `Orders`-Entitätenmenge zurückgegeben:  
  
     [!code-csharp[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetailsspecific)]  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] beschränkt die Anzahl von Entitätenmengen, die mit der `$expand`-Abfrageoption in einer einzelnen Abfrage enthalten sein können, auf 12.  
  
-   **Explizites Laden**: Rufen Sie die <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> Methode für die <xref:System.Data.Services.Client.DataServiceContext> Instanz, um verknüpfte Entitäten explizit zu laden. Jeder Aufruf der <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>-Methode erstellt eine separate Anforderung an den Datendienst. Im folgenden Beispiel werden `Order_Details` für eine `Orders`-Entität explizit geladen:  
  
     [!code-csharp[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedorderdetailsspecific)]  
  
 Denken Sie beim Auswählen der Option daran, dass zwischen der Anzahl der Abfragen des Datendiensts und der in einer einzelnen Antwort zurückgegebenen Datenmenge abgewogen werden sollte. Verwenden Sie Eager Loading, wenn die Anwendung zugeordnete Objekte erfordert und Sie die hinzugefügte Latenzzeit von zusätzlichen Anforderungen zum expliziten Abrufen vermeiden möchten. Allerdings sollten Sie in Fällen, wenn die Anwendung die Daten nur für bestimmte verknüpfte Entitätsinstanzen benötigt, das explizite Laden dieser Entitäten durch Aufrufen der <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>-Methode in Betracht ziehen. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von verbundenen Entitäten](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md).  
  
## <a name="paged-content"></a>Ausgelagerter Inhalt  
 Wenn Paging im Datendienst aktiviert ist, ist die Anzahl von Einträgen im Feed, die der Datendienst zurückgibt, durch die Konfiguration des Datendiensts beschränkt. Seitenbeschränkungen können für jede Entitätenmenge separat festgelegt werden. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md). Wenn Paging aktiviert ist, enthält der abschließende Eintrag im Feed einen Link zur nächsten Seite mit Daten. Dieser Link ist in einem <xref:System.Data.Services.Client.DataServiceQueryContinuation%601>-Objekt enthalten. Sie erhalten den URI zur nächsten Seite mit Daten, indem Sie die <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>-Methode für die <xref:System.Data.Services.Client.QueryOperationResponse%601> aufrufen, die beim Ausführen der <xref:System.Data.Services.Client.DataServiceQuery%601> zurückgegeben wird. Das zurückgegebene <xref:System.Data.Services.Client.DataServiceQueryContinuation%601>-Objekt wird dann verwendet, um die nächste Seite mit Ergebnissen zu laden. Sie müssen vor dem Aufrufen der <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>-Methode das Abfrageergebnis aufzählen. Verwenden Sie eine `do…while`-Schleife, um zuerst das Abfrageergebnis aufzuzählen und dann den nächsten `non-null`-Linkwert zu suchen. Wenn die <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>-Methode `null` (`Nothing` in Visual Basic) zurückgibt, sind keine zusätzlichen Ergebnisseiten für die ursprüngliche Abfrage vorhanden. Im folgenden Beispiel wird eine `do…while`-Schleife gezeigt, die ausgelagerte Kundendaten aus dem Northwind-Beispieldatendienst lädt.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextlink)]
 [!code-vb[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextlink)]  
  
 Wenn eine Abfrage anfordert, dass verknüpfte Entitäten in einer einzelnen Antwort zusammen mit der angeforderten Entitätenmenge zurückgegeben werden, wirken sich Paginggrenzen möglicherweise auf geschachtelte Feeds aus, die inline in der Antwort enthalten sind. Wenn beispielsweise eine Paginggrenze im Northwind-Beispieldatendienst für die `Customers`-Entitätenmenge festgelegt wird, kann eine unabhängige Paginggrenze auch für die verknüpfte `Orders`-Entitätenmenge festgelegt werden, wie im folgenden Beispiel für die Datei Northwind.svc.cs, die den Northwind-Beispieldatendienst definiert.  
  
 [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
 [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
 In diesem Fall müssen Sie Paging sowohl für die `Customers`-Entitätenmenge der obersten Ebene als auch die geschachtelte `Orders`-Entitätenmenge implementieren. Im folgenden Beispiel wird die `while`-Schleife gezeigt, mit der Seiten von `Orders`-Entitäten geladen werden, die mit einer ausgewählten `Customers`-Entität verknüpft sind.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextorderslink)]
 [!code-vb[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextorderslink)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Laden von ausgelagerten Ergebnissen](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md).  
  
## <a name="binary-data-streams"></a>Binäre Datenströme  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, auf BLOB (Binary Large Object)-Daten als Datenstrom zuzugreifen. Streaming verzögert das Laden binärer Daten, bis sie benötigt werden, und der Client kann diese Daten effizienter verarbeiten. Um diese Funktionalität zu nutzen, muss der Datendienst den <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Anbieter implementieren. Weitere Informationen finden Sie unter [Streaminganbieter](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md). Wenn Streaming aktiviert ist, werden Entitätstypen ohne die verknüpften binären Daten zurückgegeben. In diesem Fall müssen Sie verwenden die <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> Methode der <xref:System.Data.Services.Client.DataServiceContext> Klasse, um den Datenstrom für die binären Daten aus dem Dienst zuzugreifen. Verwenden Sie entsprechend die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>-Methode, um binäre Daten für eine Entität als Datenstrom hinzuzufügen oder zu ändern. Weitere Informationen finden Sie unter [arbeiten mit Binärdaten](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
