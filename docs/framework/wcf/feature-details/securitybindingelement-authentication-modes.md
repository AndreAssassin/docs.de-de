---
title: SecurityBindingElement-Authentifizierungsmodi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
ms.openlocfilehash: 2aed766e6b2da7ebaf7b5b863375ee95b99eb159
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748466"
---
# <a name="securitybindingelement-authentication-modes"></a>SecurityBindingElement-Authentifizierungsmodi
Windows Communication Foundation (WCF) bietet verschiedene Modi, die mit denen Clients und Dienste gegenseitig authentifizieren. Sie können Sicherheitsbindungselemente für diese Authentifizierungsmodi erstellen. Dazu verwenden Sie statische Methoden für die <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse oder führen eine entsprechende Konfiguration durch. In diesem Thema werden die 18 Authentifizierungsmodi kurz beschrieben.  
  
 Ein Beispiel der Verwendung des Elements für einen der Authentifizierungsmodi finden Sie unter [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="basic-configuration-programming"></a>Programmgesteuerte Konfiguration  
 Im folgenden Verfahren wird beschrieben, wie der Authentifizierungsmodus in einer Konfigurationsdatei festgelegt wird.  
  
#### <a name="to-set-the-authentication-mode-in-configuration"></a>So legen Sie den Authentifizierungsmodus in der Konfiguration fest  
  
1. Um die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) -Element, Hinzufügen einer [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2. Hinzufügen als ein untergeordnetes Element eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element der `<customBinding>` Element.  
  
3. Fügen Sie dem `<security>`-Element ein `<binding>`-Element hinzu.  
  
4. Legen Sie das `authenticationMode`-Attribut auf einen der unten beschriebenen Werte fest. Im folgenden Codebeispiel wird der Modus auf `AnonymousForCertificate` festgelegt.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### <a name="to-set-the-mode-programmatically"></a>So legen Sie den Modus programmgesteuert fest  
  
1. Beim Rückgabetyp kann es sich um einen der folgenden handeln: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> oder <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2. Rufen Sie die entsprechende statische Methode der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse auf. Im folgenden Codebeispiel wird die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>-Methode aufgerufen.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3. Verwenden Sie das Bindungselement, um die benutzerdefinierte Bindung zu erstellen. Weitere Informationen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="mode-descriptions"></a>Modusbeschreibungen  
  
### <a name="anonymousforcertificate"></a>AnonymousForCertificate  
 In diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>. Alternativ Festlegen der `authenticationMode` Attribut der <`security`>-Element `AnonymousForCertificate`.  
  
### <a name="anonymousforsslnegotiated"></a>AnonymousForSslNegotiated  
 In diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird über ein X.509-Zertifikat authentifiziert, das zur Laufzeit verhandelt wird. Das Sicherheitsbindungselement ist ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, das von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>-Methode zurückgegeben wird, wenn für den ersten Parameter der Wert `false` übergeben wird. Legen Sie das `authenticationMode`-Attribut alternativ auf `AnonymousForSslNegotiated` fest.  
  
### <a name="certificateovertransport"></a>CertificateOverTransport  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das an der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, d.&amp;#160;h. ein Token, das die Nachricht signiert. Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert. Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `CertificateOverTransport` fest.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert. Der Dienst wird nicht am Client authentifiziert. Stattdessen verschlüsselt der Sicherheitstokendienst den freigegebenen Schlüssel als Teil des ausgestellten Tokens, sodass nur der Dienst den Schlüssel entschlüsseln kann. Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `IssuedToken` fest.  
  
### <a name="issuedtokenforcertificate"></a>IssuedTokenForCertificate  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert. Das ausgegebene Token wird an der SOAP-Schicht als unterstützendes Token bzw. Bearer-Token angezeigt, d. h. als ein Token, das die Nachricht signiert. Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert. Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `IssuedTokenForCertificate` fest.  
  
### <a name="issuedtokenforsslnegotiated"></a>IssuedTokenForSslNegotiated  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert. Das ausgegebene Token wird an der SOAP-Schicht als unterstützendes Token bzw. Bearer-Token angezeigt, d. h. als ein Token, das die Nachricht signiert. Der Dienst wird über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `IssuedTokenForSslnegotiated` fest.  
  
### <a name="issuedtokenovertransport"></a>IssuedTokenOverTransport  
 Bei diesem Authentifizierungsmodus wird der Client nicht am Dienst selbst authentifiziert. Er wird stattdessen an einem Sicherheitstokendienst authentifiziert und empfängt ein SAML-Token, das er dem Server als Beleg für den freigegebenen Schlüssel präsentiert. Das ausgegebene Token wird an der SOAP-Schicht als unterstützendes Token bzw. Bearer-Token angezeigt, d. h. als ein Token, das die Nachricht signiert. Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert. Das Sicherheitsbindungselement ist ein von der `TransportSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `IssuedTokenOverTransport` fest.  
  
### <a name="kerberos"></a>Kerberos  
 In diesem Authentifizierungsmodus wird der Client über ein Kerberos-Ticket am Dienst authentifiziert. Dieses gleiche Ticket bietet auch Serverauthentifizierung. Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `Kerberos` fest.  
  
> [!NOTE]
>  Um diesen Authentifizierungsmodus zu verwenden, muss dem Dienstkonto ein Dienstprinzipalname zugeordnet sein. Führen Sie den Dienst zu diesem Zweck unter dem Konto NETZWERKDIENST oder dem Konto LOKALES SYSTEM aus. Verwenden Sie andernfalls das Tool SetSpn.exe, um einen Dienstprinzipalnamen für das Dienstkonto zu erstellen. Der Client muss in jedem Fall den korrekten Dienstprinzipalnamen im Verwenden der [ \<ServicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) -Element, oder mithilfe der <xref:System.ServiceModel.EndpointAddress> Konstruktor. Weitere Informationen finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
> [!NOTE]
>  Wenn der `Kerberos`-Authentifizierungsmodus verwendet wird, werden die <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>-Ebene und die <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>-Ebene des Identitätswechsels nicht unterstützt.  
  
### <a name="kerberosovertransport"></a>KerberosOverTransport.  
 In diesem Authentifizierungsmodus wird der Client über ein Kerberos-Ticket am Dienst authentifiziert. Das Kerberos-Token wird an der SOAP-Schicht als unterstützendes Token angezeigt, d.&amp;#160;h. ein Token, das die Nachricht signiert. Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert. Das Sicherheitsbindungselement ist ein von der `TransportSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `KerberosOverTransport` fest.  
  
> [!NOTE]
>  Um diesen Authentifizierungsmodus zu verwenden, muss dem Dienstkonto ein Dienstprinzipalname zugeordnet sein. Führen Sie den Dienst zu diesem Zweck unter dem Konto NETZWERKDIENST oder dem Konto LOKALES SYSTEM aus. Verwenden Sie andernfalls das Tool SetSpn.exe, um einen Dienstprinzipalnamen für das Dienstkonto zu erstellen. Der Client muss in jedem Fall den korrekten Dienstprinzipalnamen im Verwenden der [ \<ServicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) -Element, oder mithilfe der <xref:System.ServiceModel.EndpointAddress> Konstruktor. Weitere Informationen finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
### <a name="mutualcertificate"></a>MutualCertificate  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das an der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, d.&amp;#160;h. ein Token, das die Nachricht signiert. Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `MutualCertificate` fest.  
  
### <a name="mutualcertificateduplex"></a>MutualCertificateDuplex  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das an der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, d.&amp;#160;h. ein Token, das die Nachricht signiert. Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der `AsymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `MutualCertificateDuplex` fest.  
  
### <a name="mutualsslnegotiated"></a>MutualSslNegotiated  
 In diesem Authentifizierungsmodus werden sowohl der Client als auch der Dienst über X.509-Zertifikate authentifiziert. Das Sicherheitsbindungselement ist ein `SymmetricSecurityBindingElement`, das von der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A>-Methode zurückgegeben wird, wenn für den ersten Parameter der Wert `true` übergeben wird. Legen Sie das `authenticationMode`-Attribut alternativ auf `MutualSslNegotiated` fest.  
  
### <a name="secureconversation"></a>SecureConversation  
 Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>. Diese Methode verwendet ein <xref:System.ServiceModel.Channels.SecurityBindingElement> als Parameter, der während der Initialisierung zum Erstellen der sicheren Sitzung verwendet wird. Legen Sie das `authenticationMode`-Attribut alternativ auf `SecureConversation` fest.  
  
 Falls keine Bootstrapbindung angegeben ist, wird der `SspiNegotiated`-Authentifizierungsmodus verwendet.  
  
### <a name="sspinegotiation"></a>SspiNegotiation  
 In diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll für die Client- und Serverauthentifizierung verwendet. Falls möglich, wird Kerberos verwendet, andernfalls NTLM. Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `SspiNegotiated` fest.  
  
### <a name="sspinegotiatedovertransport"></a>SspiNegotiatedOverTransport  
 In diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll für die Client- und Serverauthentifizierung verwendet. Falls möglich, wird Kerberos verwendet, andernfalls NTLM. Das resultierende Token wird an der SOAP-Schicht als unterstützendes Token angezeigt, d.&amp;#160;h. ein Token, das die Nachricht signiert. Der Dienst wird zusätzlich auf der Transportschicht über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der `TransportSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `SspiNegotiatedOverTransport` fest.  
  
### <a name="usernameforcertificate"></a>UserNameForCertificate  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert. Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert. Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `UserNameForCertificate` fest.  
  
 Für den `UserNameForCertificate`-Authentifizierungsmodus müssen sowohl der Client als auch der Dienst WS-Sicherheit 1.1 verwenden.  
  
### <a name="usernameforsslnegotiated"></a>UserNameForSslNegotiated  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert. Der Dienst wird über ein X.509-Zertifikat authentifiziert. Das Sicherheitsbindungselement ist ein von der `SymmetricSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `UserNameForSslNegotiated` fest.  
  
### <a name="usernameovertransport"></a>UserNameOverTransport  
 In diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das an der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird. Dieses Token wird von der Nachrichtensignatur signiert. Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert. Das Sicherheitsbindungselement ist ein von der `TransportSecurityBindingElement`-Methode zurückgegebenes <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A>. Legen Sie das `authenticationMode`-Attribut alternativ auf `UserNameOverTransport` fest.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
