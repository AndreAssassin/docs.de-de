---
title: 'Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7df6ec57204990066ce59700e5c2582701f2a81a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045916"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements

Wenn ein Benutzername und ein Kennwort für die Authentifizierung verwendet werden, werden von Windows Communication Foundation (WCF) standardmäßig Windows verwendet, um den Benutzernamen und das Kennwort zu überprüfen. WCF ermöglicht jedoch benutzerdefinierte Authentifizierungs Schemas für Benutzernamen und Kennwort, die auch als *Validierungs Steuerelemente*bezeichnet werden. Zum Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements erstellen und konfigurieren Sie eine Klasse, die sich von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> ableitet.

Eine Beispielanwendung finden Sie unter [Benutzer Name Kennwort-Validierungs](../../../../docs/framework/wcf/samples/user-name-password-validator.md)Steuerelement.

### <a name="to-create-a-custom-user-name-and-password-validator"></a>So erstellen Sie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement

1. Erstellen Sie eine von der <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>-Klasse abgeleitete Klasse.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. Implementieren Sie ein benutzerdefiniertes Authentifizierungsschema, indem Sie die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode außer Kraft setzen.

    Verwenden Sie nicht den Code des folgenden Beispiels, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt. Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.

    Um dem Client Authentifizierungsfehler zurückzugeben, lösen Sie in der <xref:System.ServiceModel.FaultException>-Methode eine <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> aus.

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>So konfigurieren Sie einen Dienst für das Verwenden eines benutzerdefinierten Benutzernamen- und Kennwort-Validierungssteuerelements

1. Konfigurieren Sie eine Bindung, die Nachrichtensicherheit über jedes beliebige Transportprotokoll oder Sicherheit auf Transportebene über HTTP(S) verwendet.

    Wenn Sie die Nachrichten Sicherheit verwenden, fügen Sie eine der vom System bereitgestellten Bindungen hinzu, z. b. eine [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)oder eine [ \<CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) - `UserName` >, die die Nachrichten Sicherheit und den Anmelde Informationstyp unterstützt.

    Wenn Sie Sicherheit auf Transport Ebene über HTTP (S) verwenden, fügen Sie entweder das [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oder [ \<BasicHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), eine [ \<NetTcpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) oder eine [ \<CustomBinding-> ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), die HTTP (S) und das `Basic` Authentifizierungsschema verwendet.

    > [!NOTE]
    > Wenn Sie [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] oder höher verwenden, können Sie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement mit Nachrichten- und Transportsicherheit nutzen. Mit WinFX kann ein benutzerdefinierter Benutzername und ein Kennwort-Validierungs Steuerelement nur mit Nachrichten Sicherheit verwendet werden.

    > [!TIP]
    > Weitere Informationen zur Verwendung von \<NetTcpBinding > in diesem Kontext finden [ \<Sie unter Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)

    1. Fügen Sie in der Konfigurationsdatei unter dem [ \<System. Service Model >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) -Element eine [ \<-Bindung >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) -Element hinzu.

    2. Fügen Sie dem Bindungs Abschnitt eine [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oder [ \<ein BasicHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element hinzu. Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden [Sie unter Gewusst wie: Geben Sie eine Dienst Bindung in](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)der Konfiguration an.

    3. Legen Sie `mode` das-Attribut [ \<der Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) oder [ \<des Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) auf `Message`, `TransportWithMessageCredential` `Transport`oder fest.

    4. Legen Sie `clientCredentialType` das-Attribut [ \<der Nachrichten >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oder [ \<des Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)fest.

        Wenn Sie die Nachrichten Sicherheit verwenden, `clientCredentialType` legen Sie das-Attribut [ \<der Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) auf `UserName`fest.

        Wenn Sie Sicherheit auf Transport Ebene über HTTP (S) verwenden, legen `clientCredentialType` Sie das-Attribut [ \<der Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) oder [ \<Transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) auf `Basic`fest.

        > [!NOTE]
        > Wenn ein WCF-Dienst mit Sicherheit auf Transport Ebene in Internetinformationsdienste (IIS) gehostet wird und <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> die-Eigenschaft auf <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>festgelegt ist, wird für das benutzerdefinierte Authentifizierungsschema eine Teilmenge der Windows-Authentifizierung verwendet. Der Grund hierfür ist, dass IIS in diesem Szenario die Windows-Authentifizierung ausführt, bevor WCF den benutzerdefinierten Authentifikator aufruft.

    Weitere Informationen zum Erstellen eines WCF-Bindungs Elements finden [Sie unter Gewusst wie: Geben Sie eine Dienst Bindung in](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)der Konfiguration an.

    Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. Konfigurieren Sie ein Verhalten, das angibt, dass ein benutzerdefiniertes Benutzername- und Kennwort-Validierungssteuerelement verwendet wird, um Benutzernamen/Kennwort-Paare für eingehende <xref:System.IdentityModel.Tokens.UserNameSecurityToken>-Sicherheitstoken zu überprüfen.

    1. Fügen Sie als untergeordnetes Element für das [ \<System. Service Model >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) -Element ein [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) -Element hinzu.

    2. Fügen Sie [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) [dem Verhalten\<>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element ein Service Verhaltens> hinzu.

    3. Fügen Sie ein [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) -Element hinzu `name` , und legen Sie das-Attribut auf einen geeigneten Wert fest

    4. Fügen [Sie dem\<Behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) -Element einen [ \<servicecreden->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) hinzu.

    5. Fügen [Sie dem\<servicecredenseins->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)einen [ \<userNameAuthentication->](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) hinzu.

    6. Legen Sie `userNamePasswordValidationMode` auf `Custom` fest

        > [!IMPORTANT]
        > Wenn der `userNamePasswordValidationMode` Wert nicht festgelegt ist, verwendet WCF anstelle des benutzerdefinierten Benutzernamens und des Kennwort-Validierungs Steuer Elements die Windows-Authentifizierung.

    7. Legen Sie den `customUserNamePasswordValidatorType` auf den Typ fest, der das benutzerdefinierte Benutzernamen- und Kennwort-Validierungssteuerelement darstellt.

    Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement erstellt wird. Verwenden Sie nicht den Code, der die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode in einer Produktionsumgebung außer Kraft setzt. Ersetzen Sie den Code mit dem benutzerdefinierten Benutzernamen- und Kennwort-Validierungsschema. Möglicherweise müssen der Benutzername und das zugehörige Kennwort aus einer Datenbank abgerufen werden.

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Vorgehensweise: Verwenden des ASP.net-Mitgliedschafts Anbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
