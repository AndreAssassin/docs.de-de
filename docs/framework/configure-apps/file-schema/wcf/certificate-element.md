---
title: <certificate>-Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: eea8130911ca3780a6e4e753c17877e58c50b139
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704322"
---
# <a name="certificate-element"></a>\<Zertifikat >-Element
Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<peer>  
\<certificate>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`findValue`|Eine Zeichenfolge, die den Wert angibt, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Der in diesem Attribut enthaltene Typ muss den Anforderungen des angegebenen `x509FindType`-Werts entsprechen. Der Standardwert ist eine leere Zeichenfolge.|  
|`storeLocation`|Gibt den Speicherort des X.509-Zertifikatspeichers an, den der Client zum Prüfen des Peerzertifikats verwendet. Folgende Werte sind gültig:<br /><br /> -LocalMachine: der auf dem lokalen Computer zugewiesene Zertifikatspeicher.<br />-CurrentUser: der für den aktuellen Benutzer zugewiesene Zertifikatspeicher.<br /><br /> Die Standardeinstellung ist LocalMachine.|  
|`storeName`|Gibt den Namen des X.509-Zertifikatsspeichers an, der geöffnet werden soll. Folgende Werte sind gültig:<br /><br /> -AddressBook: Der Zertifikatspeicher für andere Benutzer.<br />-   AuthRoot: Der Zertifikatspeicher für Drittanbieter-Zertifizierungsstellen (CAs).<br />-CertificateAuthority: Der Zertifikatspeicher für Zwischenzertifizierungsstellen-Zertifikate (CAs).<br />– Nicht zulässig: Der Zertifikatspeicher für widerrufene Zertifikate.<br />-Meine: Der Zertifikatspeicher für persönliche Zertifikate.<br />-Stammverzeichnis: Der Zertifikatspeicher für vertrauenswürdige Stamm-Zertifizierungsstellen (CAs).<br />– TrustedPeople: Der Zertifikatspeicher für direkt vertrauenswürdige Personen und Ressourcen.<br />-   TrustedPublisher: Der Zertifikatspeicher für direkt vertrauenswürdige Herausgeber.<br /><br /> Der Standardwert ist My.|  
|`X509FindType`|Definiert den Typ der X.509-Suche, die ausgeführt werden soll. Folgende Werte sind gültig:<br /><br /> -   FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> Der im `findValue`-Attribut enthaltene Typ muss den Anforderungen des angegebenen `X509FindType`-Werts entsprechen.<br /><br /> Der Standardwert ist FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement enthält eine beim Authentifizieren von Nachbarn im Peermesh verwendete X509Certificate2-Instanz.  
  
 Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-zu-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code gibt an, wie das in einem Peer-to-Peer-Szenario verwendete Zertifikat gesucht wird.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Peer-to-Peer-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Benutzerdefinierter Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
