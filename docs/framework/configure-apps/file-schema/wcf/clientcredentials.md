---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157234"
---
# <a name="clientcredentials"></a>\<clientCredentials>
Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`supportInteractive`|Ein boolescher Wert, der angibt, ob ein interaktiver Benutzer in die Auswahl von Clientanmeldeinformationen zur Laufzeit einbezogen werden kann. Der Standardwert ist `true`.|  
|`type`|Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|Gibt das zum Authentifizieren des Clients am Dienst verwendete Zertifikat an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.|  
|[\<httpDigest>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|Gibt einen zum Authentifizieren des Clients am Dienst verwendeten Hashwert an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.|  
|[\<issuedToken>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Gibt einen zum Authentifizieren des Clients an einem Secure Token Service (STS) verwendeten benutzerdefinierten Tokentyp an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Gibt die aktuellen Peeranmeldeinformationen an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Gibt das zum Authentifizieren des Diensts am Client verwendete Zertifikat an und liefert eine Struktur zum Festlegen der Zertifikatsoptionen. Dieses Zertifikat muss dem Client out-of-band vom Dienst zur Verfügung gestellt werden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.|  
|[\<windows>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Gibt Windows-Anmeldeinformationen an. Der Standardwert sind die Anmeldeinformationen des aktuellen Threads. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsClientElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist. Dieser Konfigurationsabschnitt kann auch zur Angabe von Dienstzertifikaten in Szenarien verwendet werden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)
