---
title: WS 2007 Federation-HTTP-Bindung
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 550a88552658864e3eedb70463e676ad6f9a2511
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324941"
---
# <a name="ws-2007-federation-http-binding"></a>WS 2007 Federation-HTTP-Bindung
In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.WS2007FederationHttpBinding> veranschaulicht. Dabei handelt es sich um eine Standardbindung, mit der Sie verbundene Szenarien erstellen können, die die Version 1.3 der WS-Trust-Spezifikation unterstützen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Das Beispiel besteht aus einem konsolenbasierten Clientprogramm (Client.exe), einem konsolenbasierten Sicherheitstokendienstprogramm (Securitytokenservice.exe) und einem konsolenbasierten Dienstprogramm (Service.exe). Der Dienst implementiert einen Vertrag, der ein Anforderung-/Antwort-Kommunikationsmuster definiert. Der Vertrag wird durch die `ICalculator`-Schnittstelle definiert, die mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar macht. Der Client empfängt ein Sicherheitstoken vom Sicherheitstokendienst (STS) und stellt beim Dienst synchrone Anforderungen an eine bestimmte mathematische Operation. Der Dienst antwortet dann mit dem Ergebnis. Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
 Im Beispiel wird der `ICalculator`-Vertrag mit dem `ws2007FederationHttpBinding`-Element verfügbar gemacht. Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Client.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Auf der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` Wert gibt an, welcher Sicherheitsmodus verwendet werden soll. In diesem Beispiel wird `message` Sicherheit verwendet wird, wird daher die [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) angegeben ist, in der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). Die [ \<Aussteller >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) Element innerhalb der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) gibt die Adresse und Bindung für den STS an, die ein Sicherheitstoken an den Client ausgibt, damit der Client kann authentifizieren Sie sich bei der `ICalculator` Service.  
  
 Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Dienst.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Auf der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` Wert gibt an, welcher Sicherheitsmodus verwendet werden soll. In diesem Beispiel wird `message` Sicherheit verwendet wird, wird daher die [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) angegeben ist, in der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md). Die [ \<"issuermetadata" >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) Element `ws2007FederationHttpBinding` innerhalb der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) gibt die Adresse und Identität für einen Endpunkt, der zum Abrufen von verwendet werden kann die Metadaten für den STS.  
  
 Das Verhalten für den Dienst wird im folgenden Code gezeigt.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Die [ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> kann der Dienst Einschränkungen für die Token Geben sie die Clients bei der Authentifizierung ermöglicht. In dieser Konfiguration wird angegeben, dass von einem Zertifikat mit dem Ausstellernamen CN=STS signierte Token vom Dienst akzeptiert werden.  
  
 STS macht einen einzelnen Endpunkt durch die Standard-<xref:System.ServiceModel.WS2007HttpBinding> verfügbar. Der Dienst antwortet auf Token-Anforderungen von Clients. Wenn der Client mit einem Windows-Konto authentifiziert ist, gibt der Dienst ein Token aus, das den Benutzernamen des Clients als einen Anspruch enthält. Beim Erstellen des Tokens signiert STS das Token mit dem privaten Schlüssel, der dem CN=STS-Zertifikat zugeordnet ist. Außerdem wird ein symmetrischer Schlüssel erstellt und mit dem öffentlichen Schlüssel verschlüsselt, der dem CN=localhost-Zertifikat zugeordnet ist. Beim Zurückgeben des Tokens an den Client gibt STS auch den symmetrischen Schlüssel zurück. Der Client zeigt dem `ICalculator`-Dienst das ausgegebene Token und beweist, dass der symmetrische Schlüssel bekannt ist, indem die Nachricht mit diesem Schlüssel signiert wird.  
  
 Wenn Sie das Beispiel ausführen, wird die Anforderung des Sicherheitstokens im STS-Konsolenfenster angezeigt. Die Anforderungen und Antworten des Vorgangs werden im Client- und Dienstkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in einem der Konsolenfenster, um die Anwendung zu schließen.  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 Mit der in diesem Beispiel enthaltenen Datei "Setup.bat" können Sie den Server und STS mit den relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren. Die Batchdatei erstellt zwei Zertifikate im Zertifikatspeicher LocalMachine/TrustedPeople. Der Antragstellername des ersten Zertifikats lautet CN=STS. Dieses Zertifikat wird vom STS zum Signieren des Sicherheitstokens verwendet, das an den Client herausgegeben wird. Der Antragstellername des zweiten Zertifikats lautet CN=localhost. Dieses Zertifikat wird vom STS verwendet, um einen Schlüssel so zu verschlüsseln, dass er vom Dienst entschlüsselt werden kann.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie die Datei "Setup.bat", um die erforderlichen Zertifikate zu erstellen.  
  
 Diese Batchdatei verwendet Certmgr.exe und Makecert.exe, die mit dem Windows SDK verteilt werden. Sie müssen Setup.bat an einer Visual Studio-Eingabeaufforderung ausführen, sodass das Skript diese Tools finden kann.  
  
1. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
2. Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md). Bei Verwendung von [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], führen Sie Service.exe, Client.exe und SecurityTokenService.exe mit erweiterten Berechtigungen (mit der rechten Maustaste in der Dateien, und klicken Sie dann auf **als Administrator ausführen**).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
