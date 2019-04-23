---
title: 'Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse'
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 3878a94debc7066cb8ace3b119d95d3b76d91610
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322874"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a>Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse
In diesem Thema wird die Vorgehensweise beim Senden von Daten an einen Server beschrieben. Die Prozedur wird häufig verwendet, um einer Webseite Daten bereitzustellen. 
  
## <a name="to-send-data-to-a-host-server"></a>Senden von Daten an einen Hostserver  
  
1. Erstellen Sie eine <xref:System.Net.WebRequest>-Instanz, indem Sie <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> mit dem URI einer Ressource aufrufen, die Daten akzeptiert, wie z.B. ein Skript oder eine ASP.NET-Seite. Beispiel: 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")  
    ```  
  
    > [!NOTE]
    > .NET Framework stellt von den Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitete protokollspezifische Klassen für URIs bereit, die mit *http:*, *https:*, *ftp:* und *file:* beginnen.
    Wenn Sie protokollspezifische Eigenschaften festlegen oder lesen müssen, wandeln Sie Ihr <xref:System.Net.WebRequest>- oder <xref:System.Net.WebResponse>-Objekt in einen protokollspezifischen Objekttyp um. Weitere Informationen finden Sie unter [Programmieren austauschbarer Protokolle](programming-pluggable-protocols.md). 
  
2. Legen Sie alle Eigenschaftswerte, die Sie benötigen, in Ihrem `WebRequest`-Objekt fest. Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> auf eine Instanz der <xref:System.Net.NetworkCredential>-Klasse fest:
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3. Geben Sie eine Protokollmethode an, die das Senden von Daten mit einer Anforderung zulässt, wie z.B. die HTTP-Methode `POST`:  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4. Legen Sie die Eigenschaft <xref:System.Web.HttpRequest.ContentLength> auf die Anzahl von Bytes fest, die Ihre Anforderung enthält. Beispiel: 
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5. Legen Sie für die <xref:System.Web.HttpRequest.ContentType>-Eigenschaft einen geeigneten Wert fest. Beispiel:
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6. Rufen Sie den Datenstrom ab, der die Anforderungsdaten enthält, indem Sie die Methode <xref:System.Net.WebRequest.GetRequestStream%2A> aufrufen. Beispiel:
  
    ```csharp  
    Stream dataStream = request.GetRequestStream();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream()  
    ```  
  
7. Schreiben Sie die Daten in das von der `GetRequestStream`-Methode zurückgegebene <xref:System.IO.Stream>-Objekt. Beispiel:
  
    ```csharp  
    dataStream.Write(byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write(byteArray, 0, byteArray.Length)  
    ```  
  
8. Schließen Sie den Anforderungsdatenstrom durch Aufrufen der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode. Beispiel:
  
    ```csharp  
    dataStream.Close();  
    ```  
  
    ```vb  
    dataStream.Close()  
    ```  
  
9. Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält. Der Typ des zurückgegebenen `WebResponse`-Objekts wird durch das URI-Schema der Anforderung bestimmt. Beispiel:
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
10. Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften des `WebResponse`-Objekts zugreifen oder das Objekt in eine protokollspezifische Instanz umwandeln. 

    Wandeln Sie z.B. das `WebResponse`-Objekt in einen <xref:System.Net.HttpWebResponse>-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen möchten. Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen der HTTP-spezifischen Eigenschaft <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, die mit einer Antwort gesendet wird:
  
    ```csharp  
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);    
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>-Methode des `WebResponse`-Objekts auf. Beispiel:
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
12. Nachdem Sie die Daten des Antwortobjekts gelesen haben, können Sie entweder das Objekt mit der <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType>-Methode oder den Antwortdatenstrom mit der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen. Wird weder die Antwort noch der Datenstrom geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Serververbindungen und kann somit weitere Anforderungen nicht mehr verarbeiten. Da die `WebResponse.Close`-Methode beim Schließen der Antwort `Stream.Close` aufruft, ist das Aufrufen von `Close` für Antwort- und Datenstromobjekt nicht notwendig (aber auch nicht schädlich). Beispiel:
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Codebeispiel wird die Vorgehensweise beim Senden von Daten an einen Webserver und dem Lesen der Daten in der Antwort veranschaulicht:  

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a>Siehe auch

- [Erstellen von Internetanforderungen](creating-internet-requests.md)
- [Verwenden von Datenströmen im Netzwerk](using-streams-on-the-network.md)
- [Zugreifen auf das Internet über einen Proxy](accessing-the-internet-through-a-proxy.md)
- [Anfordern von Daten](requesting-data.md)
- [Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse](how-to-request-data-using-the-webrequest-class.md)
