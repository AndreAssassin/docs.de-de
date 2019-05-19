---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: f989252c7dd9b2ccdce8331e7cdd987042230ded
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880236"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst
Der ASP.NET-Rollenanbieter (in Verbindung mit dem ASP.NET-Mitgliedschaftsanbieter) ist ein Feature, mit der Entwickler von ASP.NET zum Erstellen von Websites, mit denen Benutzer ein Konto mit einem Standort erstellen und Rollen für die Autorisierung zugewiesen werden können. Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (eine Kombination aus Benutzername/Kennwort) angibt, die Site und ihre Dienste nutzen.  
  
 Eine beispielanwendung finden Sie unter [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Weitere Informationen über die ASP.NET-mitgliedschaftsanbieterfunktion finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen. Windows Communication Foundation (WCF)-Entwickler können diese Funktionen für Sicherheitszwecke nutzen. Wenn in einer WCF-Anwendung integriert, müssen Benutzer über eine Kombination aus Benutzername und Kennwort an die WCF-Clientanwendung angeben. Um WCF zur Verwendung der Datenbank zu aktivieren, müssen Sie erstellen eine Instanz von der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Klasse, legen dessen <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Eigenschaft <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, und fügen Sie die Instanz, auf die Auflistung von Verhaltensweisen, die die <xref:System.ServiceModel.ServiceHost> , die den Dienst hostet.  
  
### <a name="to-configure-the-role-provider"></a>So konfigurieren Sie den Rollenanbieter  
  
1. In der Datei "Web.config" unter der <`system.web`>-Element hinzufügen einer <`roleManager`> Element, und legen seine `enabled` -Attribut auf `true`.  
  
2. Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.  
  
3. Als untergeordnetes Element der <`roleManager`>-Element hinzufügen einer <`providers`> Element.  
  
4. Als untergeordnetes Element der <`providers`>-Element, Hinzufügen einer <`add`>-Element mit den folgenden Attributen festgelegt wird, auf die entsprechenden Werte: `name`, `type`, `connectionStringName`, und `applicationName`, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a>So konfigurieren Sie den Dienst für die Verwendung des Rollenanbieters  
  
1. In der Datei "Web.config" Hinzufügen einer [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element.  
  
2. Hinzufügen einer [ \<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Element, das <`system.ServiceModel`> Element.  
  
3. Hinzufügen einer [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) auf der <`behaviors`> Element.  
  
4. Hinzufügen einer [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert.  
  
5. Hinzufügen einer [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) auf der <`behavior`> Element.  
  
6. Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.  
  
7. Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest. Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
