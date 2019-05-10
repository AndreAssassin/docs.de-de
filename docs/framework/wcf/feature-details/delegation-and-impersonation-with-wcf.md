---
title: Delegierung und Identitätswechsel mit WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- impersonation [WCF]
- delegation [WCF]
ms.assetid: 110e60f7-5b03-4b69-b667-31721b8e3152
ms.openlocfilehash: 4f86636cd244ce53ed00f80b38777e78a3278d6f
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912503"
---
# <a name="delegation-and-impersonation-with-wcf"></a>Delegierung und Identitätswechsel mit WCF
Der*Identitätswechsel* ist ein gängiges Verfahren, das Dienste verwenden, um den Clientzugriff auf die Ressourcen einer Dienstdomäne zu beschränken. Dienstdomänenressourcen können entweder Computerressourcen, wie lokale Dateien (Identitätswechsel), oder eine Ressource auf einem anderen Computer, z. B. eine Dateifreigabe (Delegierung), sein. Eine Beispielanwendung finden Sie unter [Impersonating the Client](../../../../docs/framework/wcf/samples/impersonating-the-client.md). Ein Beispiel zur Verwendung von Identitätswechsel finden Sie unter [Vorgehensweise: Annehmen der Clientidentität für einen Dienst](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md).  
  
> [!IMPORTANT]
>  Beim Identitätswechsel eines Clients in einem Dienst wird der Dienst mit den Anmeldeinformationen des Clients ausgeführt, die höhere Rechte besitzen können als der Serverprozess.  
  
## <a name="overview"></a>Übersicht  
 In der Regel ruft ein Client einen Dienst auf, damit dieser eine Aktion für ihn ausführt. Der Identitätswechsel ermöglicht es dem Dienst, während der Ausführung der Aktion als Client zu fungieren. Die Delegierung ermöglicht es einem Front-End-Dienst, die Clientanforderung so an einen Back-End-Dienst weiterzuleiten, dass auch der Back-End-Dienst die Identität des Clients annehmen kann. Der Identitätswechsel wird meist als Möglichkeit verwendet, mit der überprüft werden kann, ob ein Client zur Durchführung einer bestimmten Aktion berechtigt ist. Die Delegierung stellt dagegen eine Möglichkeit dar, die Fähigkeit zum Identitätswechsel und die Clientidentität an einen Back-End-Dienst zu übertragen. Die Delegierung ist eine Windows-Domänenfunktion, die verwendet werden kann, wenn eine auf Kerberos basierende Authentifizierung durchgeführt wird. Delegierung und Identitätsübergabe sind zwei verschiedene Dinge. Weil bei der Delegierung die Fähigkeit zur Annahme der Identität des Clients übertragen wird, ohne das Kennwort des Clients zu besitzen, handelt es sich um einen Vorgang mit höheren Sicherheitsberechtigungen als die Identitätsübergabe.  
  
 Sowohl Identitätswechsel als auch Delegierung erfordern, dass der Client eine Windows-Identität besitzt. Wenn der Client keine Windows-Identität besitzt, dann besteht nur die Möglichkeit, die Identität des Clients dem zweiten Dienst zu übertragen.  
  
## <a name="impersonation-basics"></a>Grundlagen des Identitätswechsels  
 Windows Communication Foundation (WCF) unterstützt den Identitätswechsel für eine Vielzahl von Clientanmeldeinformationen. In diesem Thema wird die Dienstmodellunterstützung für den Identitätswechsel des Aufrufers während der Implementierung einer Dienstmethode beschrieben. Die interoperabilitätsbestrebungen von werden allgemeine Bereitstellungsszenarien, die im Zusammenhang mit Identitätswechsel und SOAP-Sicherheit und WCF-Optionen in diesen Szenarien.  
  
 In diesem Thema liegt der Schwerpunkt auf dem Identitätswechsel und Delegierung in WCF bei Verwendung der SOAP-Sicherheit. Außerdem können Sie Identitätswechsel und Delegierung mit WCF Wenn transportsicherheit nutzen, wie in beschrieben [Using Impersonation with Transport Security](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md).  
  
## <a name="two-methods"></a>Zwei Methoden  
 WCF-SOAP-Sicherheit verfügt über zwei unterschiedliche Methoden zum Durchführen von Identitätswechsel. Die verwendete Methode hängt von der Bindung ab. Die eine Methode besteht im Identitätswechsel von einem Windows-Token aus, das von SSPI (Security Support Provider Interface) oder der Kerberos-Authentifizierung stammt, die dann im Cache des Diensts gespeichert wird. Die zweite Methode besteht im Identitätswechsel von einem Windows-Token aus, das von Kerberos-Erweiterungen stammt, insgesamt als *Service-for-User* (S4U) bezeichnet.  
  
### <a name="cached-token-impersonation"></a>Identitätswechsel mit im Cache gespeichertem Token  
 Sie können einen Identitätswechsel mit einem im Cache gespeicherten Token folgendermaßen ausführen:  
  
- Mit<xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>und <xref:System.ServiceModel.NetTcpBinding> mit Windows-Clientanmeldeinformationen.  
  
- Mit<xref:System.ServiceModel.BasicHttpBinding> , mit einem <xref:System.ServiceModel.BasicHttpSecurityMode> , der auf die <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> -Anmeldeinformationen eingestellt ist, oder einer anderen Standardbindung, bei der der Client Benutzernamen-Anmeldeinformationen präsentiert, die der Dienst einem gültigen Windows-Konto zuordnen kann.  
  
- Mit jeder <xref:System.ServiceModel.Channels.CustomBinding> , die Windows-Clientanmeldeinformationen verwendet, bei denen `requireCancellation` auf `true`eingestellt ist. (Die Eigenschaft ist für folgende Klassen verfügbar: <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>, <xref:System.ServiceModel.Security.Tokens.SslSecurityTokenParameters> und <xref:System.ServiceModel.Security.Tokens.SspiSecurityTokenParameters>.) Bei Verwendung einer sicheren Konversation auf der Bindung muss die `requireCancellation`-Eigenschaft auch auf `true` eingestellt sein.  
  
- Mit jeder <xref:System.ServiceModel.Channels.CustomBinding> , bei der der Client Benutzernamen-Anmeldeinformationen präsentiert. Bei Verwendung einer sicheren Konversation auf der Bindung muss die `requireCancellation` -Eigenschaft auch auf `true`eingestellt sein.  
  
### <a name="s4u-based-impersonation"></a>Auf S4U basierender Identitätswechsel  
 Sie können einen auf S4U basierenden Identitätswechsel folgendermaßen ausführen:  
  
- Mit<xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSDualHttpBinding>und <xref:System.ServiceModel.NetTcpBinding> mit Zertifikatclient-Anmeldeinformationen, die der Dienst einem gültigen Windows-Konto zuordnen kann.  
  
- Mit jeder <xref:System.ServiceModel.Channels.CustomBinding> , die Windows-Clientanmeldeinformationen verwendet, bei denen die `requireCancellation` -Eigenschaft auf `false`eingestellt ist.  
  
- Mit jeder <xref:System.ServiceModel.Channels.CustomBinding> , die einen Benutzernamen oder Windows-Clientanmeldeinformationen und eine sichere Konversation verwendet, wobei die `requireCancellation` -Eigenschaft auf `false`eingestellt ist.  
  
 Inwieweit der Dienst die Identität des Clients annehmen kann, hängt von den Rechten ab, die das Dienstkonto beim Versuch des Identitätswechsels besitzt, vom verwendeten Typ des Identitätswechsels und möglicherweise vom Ausmaß des Identitätswechsels, den der Client zulässt.  
  
> [!NOTE]
>  Wenn Client und Dienst auf demselben Computer ausgeführt werden und der Client unter einem Systemkonto (z. B. unter `Local System` oder `Network Service`) ausgeführt wird, kann kein Clientidentitätswechsel vorgenommen werden, wenn mit Token für den Sicherheitszustandskontext eine Sicherheitsverbindung hergestellt wird. Eine Windows Forms- oder Konsolenanwendung wird in der Regel unter dem derzeit angemeldeten Konto ausgeführt, sodass für dieses Konto standardmäßig ein Identitätswechsel durchgeführt werden kann. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Seite handelt, die auf [!INCLUDE[iis601](../../../../includes/iis601-md.md)] oder [!INCLUDE[iisver](../../../../includes/iisver-md.md)]gehostet wird, wird der Client standardmäßig unter dem `Network Service` -Konto ausgeführt. Alle vom System bereitgestellten Bindungen, die Sicherheitssitzungen unterstützen, verwenden standardmäßig ein zustandsloses Token für den Sicherheitskontext. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Seite handelt und sichere Sitzungen mit zustandsbehafteten SCTs verwendet werden, kann kein Clientidentitätswechsel durchgeführt werden. Weitere Informationen zur Verwendung von zustandsbehafteten SCTs in einer sicheren Sitzung finden Sie unter [Vorgehensweise: Erstellen Sie einen Sicherheitskontext für eine sichere Sitzung Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
## <a name="impersonation-in-a-service-method-declarative-model"></a>Identitätswechsel in einer Dienstmethode: Deklaratives Modell  
 Die meisten Identitätswechselszenarien umfassen das Ausführen der Dienstmethode im Aufruferkontext. WCF bietet eine Identitätswechselfunktion, die dadurch erleichtert, indem der Benutzer an die Identitätswechsel-Anforderung in die <xref:System.ServiceModel.OperationBehaviorAttribute> Attribut. Z. B. in den folgenden Code, die WCF-Infrastruktur nimmt die Identität des Aufrufers vor dem Ausführen der `Hello` Methode. Jeder Versuch, auf die systemeigenen Ressourcen innerhalb der `Hello` -Methode zuzugreifen, ist nur erfolgreich, wenn die Zugriffsteuerungsliste der Ressource dem Aufrufer Zugriffsrechte erlaubt. Zum Aktivieren des Identitätswechsels legen Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> -Eigenschaft auf einen der <xref:System.ServiceModel.ImpersonationOption> -Enumerationswerte fest, entweder auf <xref:System.ServiceModel.ImpersonationOption.Required?displayProperty=nameWithType> oder auf <xref:System.ServiceModel.ImpersonationOption.Allowed?displayProperty=nameWithType>, wie im folgenden Beispiel dargestellt.  
  
> [!NOTE]
>  Wenn ein Dienst höhere Anmeldeinformationen besitzt als der Remoteclient, werden die Anmeldeinformationen des Diensts verwendet, wenn die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> -Eigenschaft auf <xref:System.ServiceModel.ImpersonationOption.Allowed>eingestellt ist. Wenn also ein Benutzer mit niedrigen Rechten seine Anmeldeinformationen angibt, führt ein Dienst mit höheren Rechten die Methode mit den Anmeldeinformationen des Diensts aus und kann Ressourcen verwenden, die der Benutzer mit den niedrigen Rechten sonst keinesfalls verwenden könnte.  
  
 [!code-csharp[c_ImpersonationAndDelegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#1)]
 [!code-vb[c_ImpersonationAndDelegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#1)]  
  
 Die WCF-Infrastruktur kann die Identität des Aufrufers nur dann, wenn der Aufrufer mit Anmeldeinformationen authentifiziert wird, die ein Windows-Benutzerkonto zugeordnet werden können. Wenn der Dienst für die Authentifizierung mit Anmeldeinformationen konfiguriert ist, die keinem Windows-Konto zugeordnet werden können, wird die Dienstmethode nicht ausgeführt.  
  
> [!NOTE]
>  Unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)]schlägt der Identitätswechsel beim Erstellen eines zustandsbehafteten SCT fehl, was zu einer <xref:System.InvalidOperationException>führt. Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="impersonation-in-a-service-method-imperative-model"></a>Identitätswechsel in einer Dienstmethode: Verbindliches Modell  
 Mitunter benötigt ein Aufrufer nicht die gesamte Dienstmethode für den Identitätswechsel, sondern nur einen Teil der Methode. In diesem Fall rufen Sie die Windows-Identität des Aufrufers innerhalb der Dienstmethode ab, und führen Sie den Identitätswechsel imperativ durch. Verwenden Sie dazu die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> -Eigenschaft des <xref:System.ServiceModel.ServiceSecurityContext> , um eine Instanz der <xref:System.Security.Principal.WindowsIdentity> -Klasse zurückzugeben und die <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> -Methode vor dem Verwenden der Instanz aufzurufen.  
  
> [!NOTE]
>  Achten Sie darauf, dass Sie das Visual Basic verwenden`Using` -Anweisung oder die C#- `using` Anweisung, um den Identitätswechsel automatisch rückgängig. Achten Sie Wenn Sie die Anweisung nicht verwenden oder wenn Sie eine Programmiersprache als Visual Basic oder c# verwenden, darauf, dass Sie die Identitätswechselebene zurücksetzen. Wird dies versäumt, kann dies die Grundlage für Denial-of-Service-Angriffe und Rechteerweiterungsangriffe bilden.  
  
 [!code-csharp[c_ImpersonationAndDelegation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#2)]
 [!code-vb[c_ImpersonationAndDelegation#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#2)]  
  
## <a name="impersonation-for-all-service-methods"></a>Identitätswechsel für alle Dienstmethoden  
 In einigen Fällen müssen Sie alle Methoden eines Diensts im Kontext eines Aufrufers ausführen. Statt diese Funktion explizit für jede Methode einzeln zu aktivieren, verwenden Sie das <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>. Wie im folgenden Code dargestellt, legen Sie die <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A> -Eigenschaft auf `true`fest. Das <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> wird aus den Verhaltenssammlungen der <xref:System.ServiceModel.ServiceHost> -Klasse abgerufen. Beachten Sie außerdem, dass die `Impersonation` -Eigenschaft des auf jede Methode angewendeten <xref:System.ServiceModel.OperationBehaviorAttribute> ebenfalls entweder auf <xref:System.ServiceModel.ImpersonationOption.Allowed> oder <xref:System.ServiceModel.ImpersonationOption.Required>eingestellt sein muss.  
  
 [!code-csharp[c_ImpersonationAndDelegation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#3)]
 [!code-vb[c_ImpersonationAndDelegation#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#3)]  
  
 Die folgende Tabelle beschreibt die WCF-Verhalten für alle möglichen Kombinationen von `ImpersonationOption` und `ImpersonateCallerForAllServiceOperations`.  
  
|`ImpersonationOption`|`ImpersonateCallerForAllServiceOperations`|Verhalten|  
|---------------------------|------------------------------------------------|--------------|  
|Erforderlich|n/v|WCF-Identität des Aufrufers|  
|Allowed|False|WCF ist keine Identität des Aufrufers annehmen.|  
|Allowed|true|WCF-Identität des Aufrufers|  
|NotAllowed|False|WCF ist keine Identität des Aufrufers annehmen.|  
|NotAllowed|true|Disallowed. (Eine <xref:System.InvalidOperationException> wird ausgelöst.)|  
  
## <a name="impersonation-level-obtained-from-windows-credentials-and-cached-token-impersonation"></a>Identitätswechselebene aus Windows-Anmeldeinformationen und Identitätswechsel mit im Cache gespeichertem Token  
 In einigen Szenarien besitzt der Client eine Teilkontrolle über die Ebene des Identitätswechsels, den der Dienst bei Verwendung von Windows-Clientanmeldeinformationen ausführt. Ein Szenario tritt auf, wenn der Client die Identitätswechselebene "Anonymous" angibt. Das andere Szenario liegt vor, wenn Sie einen Identitätswechsel mit einem im Cache gespeicherten Token ausführen. Legen Sie hierfür die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> -Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential> -Klasse fest, auf die als Eigenschaft der generischen <xref:System.ServiceModel.ChannelFactory%601> -Klasse zugegriffen wird.  
  
> [!NOTE]
>  Durch Angeben der Identitätswechselebene "Anonymous" meldet sich der Client anonym beim Dienst an. Der Dienst muss daher anonyme Anmeldungen zulassen, unabhängig davon, ob ein Identitätswechsel durchgeführt wird.  
  
 Der Client kann die Identitätswechselebene als <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>oder <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>angeben. Es wird nur ein Token auf der angegebenen Ebene erstellt, wie im folgenden Code veranschaulicht.  
  
 [!code-csharp[c_ImpersonationAndDelegation#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_impersonationanddelegation/cs/source.cs#4)]
 [!code-vb[c_ImpersonationAndDelegation#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_impersonationanddelegation/vb/source.vb#4)]  
  
 In der folgenden Tabelle wird die Identitätswechselebene angegeben, die der Dienst bei einem Identitätswechsel mit einem im Cache gespeicherten Token erhält.  
  
|`AllowedImpersonationLevel` -Wert|Der Dienst hat das `SeImpersonatePrivilege`|Dienst und Client sind delegierungsfähig.| `ImpersonationLevel`|  
|---------------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Anonym|Ja|n/v|Identitätswechsel|  
|Anonym|Nein|n/v|Identifikation|  
|Identifikation|n/v|n/v|Identifikation|  
|Identitätswechsel|Ja|n/v|Identitätswechsel|  
|Identitätswechsel|Nein|n/v|Identifikation|  
|Delegierung|Ja|Ja|Delegierung|  
|Delegierung|Ja|Nein|Identitätswechsel|  
|Delegierung|Nein|n/v|Identifikation|  
  
## <a name="impersonation-level-obtained-from-user-name-credentials-and-cached-token-impersonation"></a>Identitätswechselebene aus Benutzernamen-Anmeldeinformationen und Identitätswechsel mit im Cache gespeichertem Token  
 Übergeben Sie dem Dienst an, seinen Benutzernamen und Kennwort, einem Client ermöglicht WCF an, als dieser Benutzer anzumelden. dies dem Festlegen entspricht der `AllowedImpersonationLevel` Eigenschaft <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. (Die `AllowedImpersonationLevel` ist in der <xref:System.ServiceModel.Security.WindowsClientCredential>-Klasse und in der <xref:System.ServiceModel.Security.HttpDigestClientCredential>-Klasse verfügbar.) In der folgenden Tabelle wird die Identitätswechselebene angegeben, die erhalten wird, wenn der Dienst Benutzernamen-Anmeldeinformationen empfängt.  
  
|`AllowedImpersonationLevel`|Der Dienst hat das `SeImpersonatePrivilege`|Dienst und Client sind delegierungsfähig.| `ImpersonationLevel`|  
|---------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|n/v|Ja|Ja|Delegierung|  
|n/v|Ja|Nein|Identitätswechsel|  
|n/v|Nein|n/v|Identifikation|  
  
## <a name="impersonation-level-obtained-from-s4u-based-impersonation"></a>Identitätswechselebene aus einem auf S4U basierenden Identitätswechsel  
  
|Der Dienst hat das `SeTcbPrivilege`|Der Dienst hat das `SeImpersonatePrivilege`|Dienst und Client sind delegierungsfähig.| `ImpersonationLevel`|  
|----------------------------------|------------------------------------------|--------------------------------------------------|---------------------------------------|  
|Ja|Ja|n/v|Identitätswechsel|  
|Ja|Nein|n/v|Identifikation|  
|Nein|n/v|n/v|Identifikation|  
  
## <a name="mapping-a-client-certificate-to-a-windows-account"></a>Zuordnen eines Clientzertifikats zu einem Windows-Konto  
 Ein Client kann sich gegenüber einem Dienst mithilfe eines Zertifikats ausweisen; der Dienst kann angewiesen werden, den Client mittels Active Directory einem vorhandenen Konto zuzuordnen. Im folgenden XML wird gezeigt, wie der Dienst so konfiguriert wird, dass er das Zertifikat zuordnet:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="MapToWindowsAccount">  
      <serviceCredentials>  
        <clientCertificate>  
          <authentication mapClientCertificateToWindowsAccount="true" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Im folgenden Code wird gezeigt, wie der Dienst konfiguriert wird:  
  
```  
// Create a binding that sets a certificate as the client credential type.  
WSHttpBinding b = new WSHttpBinding();  
b.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a service host that maps the certificate to a Windows account.  
Uri httpUri = new Uri("http://localhost/Calculator");  
ServiceHost sh = new ServiceHost(typeof(HelloService), httpUri);  
sh.Credentials.ClientCertificate.Authentication.MapClientCertificateToWindowsAccount = true;  
```  
  
## <a name="delegation"></a>Delegierung  
 Damit ein Dienst an einen Back-End-Dienst delegiert werden kann, muss er sich gegenüber dem Back-End-Dienst mittels bilateraler (SSPI ohne Rückgriff auf NTLM) oder direkter Kerberos-Authentifizierung unter Verwendung der Windows-Identität des Clients authentifizieren. Um einen Dienst an einen Back-End-Dienst zu delegieren, erstellen Sie eine <xref:System.ServiceModel.ChannelFactory%601> und einen Kanal und leiten die Kommunikation über diesen Kanal, solange die Identität des Clients angenommen wird. Bei dieser Form der Delegierung hängt die maximale Entfernung zwischen Back-End-Dienst und Front-End-Dienst von der Identitätswechselebene des Front-End-Diensts ab. Wenn die Identitätswechselebene <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>festgelegt wird, müssen Front-End- und Back-End-Dienst auf dem gleichen Computer ausgeführt werden. Wenn die Identitätswechselebene <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>verwendet wird, können Front-End- und Back-End-Dienst auf unterschiedlichen Computern oder dem gleichen Computer ausgeführt werden. Ein Identitätswechsel auf Delegierungsebene erfordert, dass die Windows-Domänenrichtlinie entsprechend konfiguriert wurde, um eine Delegierung zuzulassen. Weitere Informationen zum Konfigurieren von Active Directory für die Delegierung finden Sie unter [Enabling Delegated Authentication](https://go.microsoft.com/fwlink/?LinkId=99690).  
  
> [!NOTE]
>  Wenn sich der Client dem Front-End-Dienst gegenüber mit einem Benutzernamen und einem Kennwort authentifiziert, die einem Windows-Konto für den Back-End-Dienst entsprechen, dann kann sich der Front-End-Dienst durch erneute Angabe des Benutzernamens und des Kennworts des Clients dem Back-End-Dienst gegenüber authentifizieren. Dies ist eine besonders mächtige Form der Identitätsübergabe, weil die Weitergabe von Benutzernamen und Kennwort an den Back-End-Dienst diesen in die Lage versetzt, einen Identitätswechsel durchzuführen. Weil Kerberos nicht verwendet wird, stellt dieser Vorgang jedoch keine Delegierung dar. Die Delegierung betreffende Active Directory-Steuerelemente gelten nicht für die Authentifizierung durch Benutzername und Kennwort.  
  
### <a name="delegation-ability-as-a-function-of-impersonation-level"></a>Delegierungsfähigkeit als Funktion der Identitätswechselebene  
  
|Ebene des Identitätswechsels|Dienst kann eine prozessübergreifende Delegierung ausführen|Dienst kann eine computerübergreifende Delegierung ausführen|  
|-------------------------|---------------------------------------------------|---------------------------------------------------|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Identification>|Nein|Nein|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>|Ja|Nein|  
|<xref:System.Security.Principal.TokenImpersonationLevel.Delegation>|Ja|Ja|  
  
 Im folgenden Codebeispiel wird die Verwendung der Delegierung veranschaulicht.  
  
 [!code-csharp[c_delegation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_delegation/cs/source.cs#1)]
 [!code-vb[c_delegation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_delegation/vb/source.vb#1)]  
  
### <a name="how-to-configure-an-application-to-use-constrained-delegation"></a>Konfigurieren einer Anwendung für die Verwendung der eingeschränkten Delegierung  
 Die eingeschränkte Delegierung kann erst verwendet werden, nachdem Absender, Empfänger und Domänencontroller entsprechend konfiguriert wurden. Die folgende Prozedur listet die Schritte auf, die eine eingeschränkte Delegierung ermöglichen. Nähere Angaben zu den Unterschieden zwischen Delegierung und eingeschränkter Delegierung finden Sie in dem Abschnitt unter [Windows Server 2003 Kerberos Extensions](https://go.microsoft.com/fwlink/?LinkId=100194) , der sich mit eingeschränkter Delegierung befasst (Seite möglicherweise auf Englisch).  
  
1. Deaktivieren Sie auf dem Domänencontroller das Kontrollkästchen **Konto ist vertraulich und kann nicht delegiert werden** für das Konto, unter dem die Clientanwendung ausgeführt wird.  
  
2. Aktivieren Sie auf dem Domänencontroller das Kontrollkästchen **Konto wird für Delegierungszwecke vertraut** für das Konto, unter dem die Clientanwendung ausgeführt wird.  
  
3. Konfigurieren Sie auf dem Domänencontroller den Computer der mittleren Schicht, sodass diesem für Delegierungszwecke vertraut wird, indem Sie auf die Option **Computer für Delegierungszwecke vertrauen** klicken.  
  
4. Konfigurieren Sie auf dem Domänencontroller den Computer der mittleren Schicht für die Verwendung der eingeschränkten Delegierung, indem Sie auf die Option **Computer nur für Delegierungszwecke angegebener Dienste vertrauen** klicken.  
  
 Ausführlichere Anweisungen zum Konfigurieren der eingeschränkten Delegierung finden Sie in den folgenden MSDN-Themen:  
  
- [Problembehandlung der Kerberos-Delegierung (Seite möglicherweise auf Englisch)](https://go.microsoft.com/fwlink/?LinkId=36724)  
  
- [Kerberos-Protokollübergang und eingeschränkte Delegierung](https://go.microsoft.com/fwlink/?LinkId=36725)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>
- <xref:System.ServiceModel.ImpersonationOption>
- <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>
- <xref:System.ServiceModel.ServiceSecurityContext>
- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ImpersonateCallerForAllOperations%2A>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- <xref:System.ServiceModel.ChannelFactory%601>
- <xref:System.Security.Principal.TokenImpersonationLevel.Identification>
- [Verwenden von Identitätswechsel mit Transportsicherheit](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)
- [Durchführen eines Identitätswechsels für den Client](../../../../docs/framework/wcf/samples/impersonating-the-client.md)
- [Vorgehensweise: Annehmen der Clientidentität für einen Dienst](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
