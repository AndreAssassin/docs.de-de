---
title: <serviceAuthorization>-Element
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834021"
---
# <a name="serviceauthorization-element"></a>\<serviceauthorization > Element

Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<verhaltensweisen >** ](behaviors.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<serviceverhaltensweisen >** ](servicebehaviors.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1serviceauthorization >**  

## <a name="syntax"></a>Syntax

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Elemente beschrieben:

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen. Die Standardeinstellung ist `false`.<br /><br /> Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.|  
|principalPermissionMode|Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen. Folgende Werte sind gültig:<br /><br /> -None<br />-UseWindowsGroups<br />-Useaspnettroles<br />-Benutzer definiert<br /><br /> Der Standardwert ist UseWindowsGroups. Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Weitere Informationen zur Verwendung dieses Attributs finden Sie unter [gewusst wie: Beschränken Sie den Zugriff mit der PrincipalPermissionAttribute-Klasse @ no__t-0.|  
|roleProviderName|Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt. Der Standardwert ist eine leere Zeichenfolge.|  
|ServiceAuthorizationManagerType|Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt. Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.|  

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|  
|-------------|-----------------|  
|authorizationPolicies|Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können. Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt. Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht. Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.|  

## <a name="remarks"></a>Hinweise

Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.  
  
Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird. Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen. Sie können auch `UseAspNetRoles` angeben, um einen benutzerdefinierten Rollen Anbieter zu verwenden, der unter dem @no__t -1System. Web >-Element konfiguriert ist, wie im folgenden Code gezeigt:

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
Der folgende Code zeigt den `roleProviderName`-Wert, der mit dem `principalPermissionMode`-Attribut verwendet wird:
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

Ein ausführliches Beispiel für die Verwendung dieses Konfigurations Elements finden Sie unter [Autorisieren des Zugriffs auf Dienst Vorgänge](../../../wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Zugriffsautorisierung für Dienstvorgänge](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst @ no__t-0
- [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse @ no__t-0
- [Autorisierungsrichtlinie](../../../wcf/samples/authorization-policy.md)
