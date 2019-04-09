---
title: 'Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 0d821ca499e0b0e9151a724de5149f35bb815861
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143259"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services)
Wenn Sie mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek auf einen Datendienst zugreifen, der das [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützt, legt die Clientbibliothek die erforderlichen HTTP-Header in Anforderungsnachrichten an den Datendienst automatisch fest. Die Clientbibliothek ist jedoch nicht in der Lage, Nachrichtenheader festzulegen, die in bestimmten Fällen erforderlich sind, z. B. wenn der Datendienst die anspruchsbasierte Authentifizierung oder Cookies erfordert. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication). In diesen Fällen müssen Sie Nachrichtenheader in der Anforderungsnachricht vor dem Senden manuell festlegen. Das Beispiel in diesem Thema zeigt, wie das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis behandelt wird, um der Anforderungsnachricht einen neuen Header hinzuzufügen, bevor sie an den Datendienst gesendet wird.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Können Sie auch die [Northwind-beispieldatendienst](https://go.microsoft.com/fwlink/?LinkId=187426) auf veröffentlichte die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Website, diese Beispieldaten Dienst ist schreibgeschützt, und um Änderungen zu speichern versuchen, einen Fehler zurück. Die beispieldatendienste auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Website lassen die anonyme Authentifizierung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis registriert und anschließend eine Abfrage für den Datendienst ausgeführt.  
  
> [!NOTE]
>  Wenn Sie bei einem Datendienst den Nachrichtenheader für jede Anforderung manuell festlegen müssen, ist es u. U. sinnvoll, den Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis durch Überschreiben der partiellen `OnContextCreated`-Methode im Entitätscontainer, der den Datendienst darstellt (in diesem Fall `NorthwindEntities`), zu registrieren.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Beispiel  
 Die folgende Methode behandelt das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis und fügt der Anforderung einen Authentifizierungsheader hinzu.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
