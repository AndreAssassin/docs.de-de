---
title: 'Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: df86f87bfc2456d77e3c1ee209cb8b4c61f53b21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140607"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters
Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Mitgliedschaftsanbieter ist eine Funktion für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Entwickler zum Erstellen von Websites, mit denen die Benutzer eindeutige Kombinationen aus Benutzername und Kennwort erstellen können. Jeder Benutzer kann damit ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (Kombination aus Benutzername und Kennwort) angibt, die Site und ihre Dienste nutzen.  
  
 Eine beispielanwendung finden Sie unter [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Informationen zur Verwendung der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -rollenanbieterfunktion finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
 Die Mitgliedschaftsfunktion setzt die Verwendung einer SQL Server-Datenbank zum Speichern der Benutzerdaten voraus. Die Funktion schließt auch Methoden zum Anzeigen einer Frage für Benutzer ein, die ihr Kennwort vergessen haben.  
  
 Windows Communication Foundation (WCF)-Entwickler können diese Funktionen für Sicherheitszwecke nutzen. Wenn in einer WCF-Anwendung integriert wird, müssen Benutzer eine Kombination aus Benutzername und Kennwort an die WCF-Clientanwendung angeben. Verwenden Sie zur Übertragung von Daten an den WCF-Dienst eine Bindung, die Benutzer/Kennwort-Anmeldeinformationen, z. B. unterstützt die <xref:System.ServiceModel.WSHttpBinding> (in der Konfiguration der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)), und legen Sie die Client-Anmeldeinformationstyp für das `UserName`. Für den Dienst, WCF-Sicherheit authentifiziert den Benutzer basierend auf den Benutzernamen und das Kennwort und weist die Rolle, die gemäß der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Rolle.  
  
> [!NOTE]
>  WCF bietet keine Methoden, um die Datenbank mit Benutzer-Kennwort-Kombinationen oder anderen Benutzerdaten zu füllen.  
  
### <a name="to-configure-the-membership-provider"></a>So konfigurieren Sie den Mitgliedschaftsanbieter  
  
1.  In der Datei "Web.config" unter der <`system.web`>-Element erstellen Sie eine <`membership`> Element.  
  
2.  Erstellen Sie unter dem `<membership>`-Element ein `<providers>`-Element.  
  
3.  Als untergeordnetes Element der <`providers`>-Element hinzufügen eine `<clear />` Element die Auflistung von Anbietern geleert.  
  
4.  Unter der `<clear />` Element erstellen ein <`add`>-Element mit den folgenden Attributen auf die entsprechenden Werte festgelegt: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, und `passwordFormat`. Das `name`-Attribut wird später als Wert in der Konfigurationsdatei verwendet. Im folgenden Beispiel wird das Attribut auf den Wert `SqlMembershipProvider` festgelegt.  
  
     Im folgenden Beispiel wird der Konfigurationsabschnitt angegeben.  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>So konfigurieren Sie Dienstsicherheit, die eine Kombination aus Benutzername und Kennwort akzeptiert  
  
1.  In der Konfigurationsdatei unter dem [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) -Element, Hinzufügen einer [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element.  
  
2.  Hinzufügen einer [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) , im Abschnitt über Bindungen. Weitere Informationen zum Erstellen einer WCF-Bindungselements finden Sie unter [Vorgehensweise: Angeben eine Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
3.  Legen Sie das `mode`-Attribut des `<security>`-Elements auf `Message` fest.  
  
4.  Festlegen der `clientCredentialType` Attribut der <`message`>-Element `UserName`. Dies gibt an, dass ein Benutzername-Kennwort-Paar als Anmeldeinformationen für den Client verwendet wird.  
  
     Das folgende Beispiel zeigt den Konfigurationscode für die Bindung.  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a>So konfigurieren Sie einen Dienst für die Verwendung des Mitgliedschaftsanbieters  
  
1.  Als untergeordnetes Element der `<system.serviceModel>` -Element, Hinzufügen einer [ \<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element  
  
2.  Hinzufügen einer [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf der <`behaviors`> Element.  
  
3.  Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) und legen Sie die `name` -Attribut auf einen geeigneten Wert.  
  
4.  Hinzufügen einer [ \<ServiceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) auf der <`behavior`> Element.  
  
5.  Hinzufügen einer [ \<UserNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) auf die `<serviceCredentials>` Element.  
  
6.  Legen Sie das `userNamePasswordValidationMode`-Attribut auf `MembershipProvider` fest.  
  
    > [!IMPORTANT]
    >  Wenn die `userNamePasswordValidationMode` Wert nicht festgelegt ist, WCF verwendet die Windows-Authentifizierung statt der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Membership-Provider.  
  
7.  Legen Sie das `membershipProviderName`-Attribut auf den Namen des Anbieters fest (wird beim Hinzufügen des Anbieters im ersten Verfahren in diesem Thema angegeben). Im folgenden Beispiel sehen Sie das `<serviceCredentials>`-Fragment bis zu diesem Punkt:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt die Konfiguration für einen Dienst, der die ASP-Mitgliedschaftsfunktion verwendet.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
