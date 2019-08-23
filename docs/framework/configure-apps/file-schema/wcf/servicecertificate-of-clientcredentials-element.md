---
title: <serviceCertificate>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: a3013d0f7efd3014892cf6400447d708809c5fcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936342"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<serviceCertificate-> \<von Clientanmelde Informationen >-Element
Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<serviceCertificate>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.|  
|[\<scopedzertifikate->](scopedcertificates-element.md)|Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden. Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|Gibt die Authentifizierungsverhalten für Dienstzertifikate an, die von einem Client verwendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement gibt die Einstellungen an, anhand derer der Client das während der SSL-Authentifizierung vom Dienst bereitgestellte Zertifikat überprüft. Enthält außerdem Zertifikate für den Dienst, die explizit auf dem Client für die Verschlüsselung von Nachrichten unter Verwendung der Nachrichtensicherheit konfiguriert sind.  
  
 Die Attribute des `serviceCertificate` -Elements sind identisch mit den Attributen [ \<des ClientCertificate->](clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
