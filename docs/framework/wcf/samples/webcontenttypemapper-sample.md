---
title: Beispiel zu WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 381fc4a3084b1a2620384a04de85b9085e02ae16
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344675"
---
# <a name="webcontenttypemapper-sample"></a>Beispiel zu WebContentTypeMapper
In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) Text Nachrichtenformate neue Inhaltstypen zugeordnet werden.  
  
 Die <xref:System.ServiceModel.Description.WebHttpEndpoint> -Element bindet den webnachrichtenencoder, dadurch kann WCF an, die JSON, XML oder unformatierte binäre Nachrichten am selben Endpunkt zu erhalten. Der Encoder bestimmt das Textformat der Nachricht, indem der HTTP-Inhaltstyp der Anforderung betrachtet wird. In diesem Beispiel wird die <xref:System.ServiceModel.Channels.WebContentTypeMapper>-Klasse eingeführt, mit der der Benutzer die Zuordnung zwischen Inhaltstyp und Textformat steuern kann.  
  
 WCF stellt einen Satz von standardzuordnungen für Inhaltstypen bereit. `application/json` wird beispielsweise JSON und `text/xml` wird XML zugeordnet. Inhaltstypen, die nicht JSON oder XML zugeordnet sind, werden dem unformatierten binären Format zugeordnet.  
  
 In einigen Szenarios (beispielsweise Push-APIs) steuert der Dienstentwickler den vom Client zurückgegebenen Inhaltstyp nicht. Beispielsweise können Clients möglicherweise JSON als `text/javascript` anstelle von `application/json` zurückgeben. In diesem Fall muss der Dienstentwickler einen von <xref:System.ServiceModel.Channels.WebContentTypeMapper> abgeleiteten Typ bereitstellen, um den jeweiligen Inhaltstyp richtig zu behandeln, wie im folgenden Beispielcode dargestellt.  
  
```  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 Der Typ muss die <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>-Methode überschreiben. Die Methode muss das `contentType`-Argument auswerten und einen der folgenden Werte zurückgeben: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> oder <xref:System.ServiceModel.Channels.WebContentFormat.Default>. Das Zurückgeben von <xref:System.ServiceModel.Channels.WebContentFormat.Default> wird für die Standardzuordnungen für den Webnachrichtenencoder zurückgestellt. Im vorhergehenden Beispielcode wird der `text/javascript`-Inhaltstyp JSON zugeordnet, und alle anderen Zuordnungen bleiben unverändert.  
  
 Gehen Sie bezüglich der WEB.CONFIG-Datei folgendermaaßen vor, um die `JsonContentTypeMapper`-Klasse zu verwenden:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Entfernen Sie das contentTypeMapper-Attribut aus der oben erwähnten Konfigurationsdatei, um die Anforderungen zum Verwenden des JsonContentTypeMapper zu überprüfen. Die Clientseite kann nicht geladen werden, wenn versucht wird, `text/javascript` zum Senden von JSON-Inhalt zu verwenden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Erstellen Sie die Projektmappe WebContentTypeMapperSample.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Navigieren Sie zu `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (Öffnen Sie JCTMClientPage.htm nicht im Browser aus dem Projektverzeichnis).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
