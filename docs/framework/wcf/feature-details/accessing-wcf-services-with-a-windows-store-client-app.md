---
title: Zugreifen auf WCF-Dienste mit einer Windows Store-Client-App
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: a7d87e6014f26842c35b0d1bf5028682a4cf69e5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294859"
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a>Zugreifen auf WCF-Dienste mit einer Windows Store-Client-App
Mit Windows 8 wird ein neuer Anwendungstyp, die so genannten Windows Store-Anwendungen, eingeführt. Diese Anwendungen sind für Touchscreenoberflächen konzipiert. .NET Framework 4.5 ermöglicht Windows Store-Anwendungen das Aufrufen von WCF-Diensten.  
  
## <a name="wcf-support-in-windows-store-applications"></a>WCF-Unterstützung in Windows Store-Anwendungen  
 Innerhalb einer Windows Store-Anwendung ist ein Teilbereich der WCF-Funktionen verfügbar. Ausführliche Informationen finden Sie in den folgenden Abschnitten.  
  
> [!IMPORTANT]
>  Verwenden Sie die WinRT-Syndication-APIs anstelle der von WCF verfügbar gemachten APIs. Weitere Informationen finden Sie unter , [WinRT-Syndication-API](https://go.microsoft.com/fwlink/?LinkId=236265)  
  
> [!WARNING]
>  Das Hinzufügen eines Webdienstverweises zu einer Windows Runtime-Komponente unter Verwendung von „Dienstverweis hinzufügen“ wird nicht unterstützt.  
  
### <a name="supported-bindings"></a>Unterstützte Bindungen  
 Die folgenden WCF-Bindungen werden in Windows Store-Anwendungen unterstützt:  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 Die folgenden Bindungselemente werden in Windows Store-Anwendungen unterstützt  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Sowohl textbasierte als auch binäre Codierungen werden unterstützt. Alle WCF-Übertragungsmodi werden unterstützt. Weitere Informationen finden Sie unter [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).  
  
### <a name="add-service-reference"></a>Dienstverweis hinzufügen  
 Um einen WCF-Dienst aus einer Windows Store-Anwendung aufzurufen, verwenden Sie die Funktion „Dienstverweis hinzufügen“ in Visual Studio 2012. Sie werden bei Verwendung von „Dienstverweis hinzufügen“ innerhalb einer Windows Store-Anwendung einige Funktionsunterschiede bemerken. Als erstes wird keine Konfigurationsdatei generiert. Da Windows Store-Anwendungen keine Konfigurationsdateien verwenden, müssen sie im Code konfiguriert werden. Dieser Konfigurationscode befindet sich in der Datei „References.cs“, die durch „Dienstverweis hinzufügen“ generiert wird. Um diese Datei anzuzeigen, müssen Sie "Alle Dateien anzeigen" Wählen Sie im Projektmappen-Explorer zur Verfügung. Die Datei befindet sich innerhalb des Projekts unter dem Knoten „Dienstverweise“ und dann „Reference.svcmap“. Alle Vorgänge, die für WCF-Dienste in einer Windows Store-Anwendung generiert werden, werden unter Verwendung des taskbasierten asynchronen Musters asynchron implementiert. Weitere Informationen finden Sie unter [asynchrone Aufgaben – asynchrone Programmierung mit Aufgaben vereinfachen](https://msdn.microsoft.com/magazine/ff959203.aspx).  
  
 Da die Konfiguration nun im Code generiert wird, werden alle Änderungen in der Datei „Reference.cs“ überschrieben, sobald der Dienstverweis aktualisiert wird. Um diese Situation zu vermeiden, wird der Konfigurationscode innerhalb einer partiellen Methode generiert, die Sie in der Clientproxyklasse implementieren können. Die partielle Methode wird folgendermaßen deklariert:  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 Sie können diese partielle Methode implementieren und die Bindung oder den Endpunkt in der Clientproxyklasse wie folgt ändern:  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {   
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,   
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a>Serialisierung  
 Die folgenden Serialisierungsprogramme werden in Windows Store-Anwendungen unterstützt:  
  
1. DataContractSerializer  
  
2. DataContractJsonSerializer  
  
3. XmlSerializer  
  
> [!WARNING]
>  „XmlDictionaryWriter.Write (DateTime)“ schreibt jetzt das DateTime-Objekt als Zeichenfolge.  
  
### <a name="security"></a>Sicherheit  

Die folgenden Sicherheitsmodi werden in Windows Store-Anwendungen unterstützt:
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
Die folgenden Clientanmeldeinformationstypen werden in Windows Store-Anwendungen unterstützt:
  
1. Keiner  
  
2. Standard  
  
3. Digest  
  
4. Negotiate  
  
5. NTLM  
  
6. Windows  
  
7. Benutzername (Nachrichtensicherheit)  
  
8. Windows (Transportsicherheit)  
  
 Damit Windows Store-Anwendungen auf standardmäßige Windows-Anmeldeinformationen zugreifen und diese senden können, müssen Sie diese Funktionalität innerhalb der Datei „Package.appmanifest“ aktivieren. Öffnen Sie diese Datei, und wählen Sie die Registerkarte "Funktionen", und wählen Sie "Standard Windows-Anmeldeinformationen". Dadurch kann die Anwendung eine Verbindung mit Intranetressourcen herstellen, die Domänenanmeldeinformationen erfordern.  
  
> [!IMPORTANT]
>  In der Reihenfolge für Windows Store-Anwendungen computerübergreifend Aufrufe ausführen können, müssen Sie eine weitere Funktion namens "Home/Work Networking" aktivieren. Diese Einstellung befindet sich ebenfalls in der Datei „Package.appmanifest“ auf der Registerkarte für Funktionen. Aktivieren Sie das Kontrollkästchen „Home/Work Networking“. Dadurch erhält die Anwendung eingehenden und ausgehenden Zugriff auf die Netzwerke der vertrauenswürdigen Orte des Benutzers wie Heim und Arbeit. Wichtige eingehende Ports sind immer blockiert. Für den Zugriff auf Internetdienste müssen Sie auch die Internetfunktion (Client) aktivieren.  
  
### <a name="misc"></a>Sonstiges  
 Die Verwendung der folgenden Klassen wird für Windows Store-Anwendungen unterstützt:  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a>Definieren von Dienstverträgen  
 Es wird empfohlen, asynchrone Dienstvorgänge nur mit dem taskbasierten asynchronen Muster zu definieren. Dadurch wird sichergestellt, dass Windows Store-Anwendungen beim Aufrufen eines Dienstvorgangs reaktionsfähig bleiben.  
  
> [!WARNING]
>  Obwohl keine Ausnahme ausgelöst wird, wenn Sie einen synchronen Vorgang definieren, wird dringend empfohlen, nur asynchrone Vorgänge zu definieren.  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a>Aufrufen von WCF-Diensten aus Windows Store-Anwendungen  
 Wie bereits erwähnt, müssen alle Konfigurationsschritte im Code vorgenommen werden, und zwar in der GetBindingForEndpoint-Methode in der generierten Proxyklasse. Ein Dienstvorgang wird genauso aufgerufen wie eine taskbasierte asynchrone Methode. Siehe dazu den folgenden Codeausschnitt.  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 Beachten Sie, dass für die Methode, die den asynchronen Aufruf ausführt, das async-Schlüsselwort und beim Aufrufen der asynchronen Methode das await-Schlüsselwort verwendet wird.  
  
## <a name="see-also"></a>Siehe auch

- [WCF in Windows Store Apps-Blog](https://blogs.msdn.com/b/piyushjo/archive/2011/09/22/wcf-in-win8-metro-styled-apps-absolutely-supported.aspx)
- [WCF Windows Store-Clients und Sicherheit](https://blogs.msdn.com/b/piyushjo/archive/2011/10/11/calling-a-wcf-service-from-a-metro-application-adding-security.aspx)
- [Windows Store-Apps und computerübergreifende Aufrufe](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)
- [Aufrufen eines in Azure bereitgestellten WCF-Diensts aus einer Windows Store-App](https://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)
- [Programmieren der WCF-Sicherheit](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [Bindungen](../../../../docs/framework/wcf/bindings.md)
