---
title: 'Vorgehensweise: Verwenden von separaten X.509-Zertifikaten zum Signieren und Verschlüsseln'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
ms.openlocfilehash: f95274861f58d1581e4c5439861ebf186b1b3489
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766942"
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a>Vorgehensweise: Verwenden von separaten X.509-Zertifikaten zum Signieren und Verschlüsseln
In diesem Thema zeigt, wie so konfigurieren Sie Windows Communication Foundation (WCF), um verschiedene Zertifikate für die nachrichtensignierung und-Verschlüsselung auf dem Client und dem Dienst verwendet wird.  
  
 Damit können verschiedene Zertifikate für Signierung und Verschlüsselung verwendet werden, müssen bei einem benutzerdefinierten Client oder Dienst Anmeldeinformationen (oder beides) erstellt werden, da WCF nicht über eine API zum Festlegen von mehreren Client- oder Dienstzertifikate bietet. Außerdem muss ein Sicherheitstokenmanager zur Verfügung gestellt werden, um die Informationen der Zertifikate zu nutzen und einen entsprechenden Sicherheitstokenanbieter für die angegebene Schlüsselverwendung und Nachrichtenrichtung zu erstellen.  
  
 Das folgende Diagramm enthält die wichtigsten verwendeten Klassen, die Klassen, von denen geerbt wird (gekennzeichnet durch einen Aufwärtspfeil), sowie die Rückgabetypen bestimmter Methoden und Eigenschaften.  
  
- `MyClientCredentials` ist eine benutzerdefinierte Implementierung von <xref:System.ServiceModel.Description.ClientCredentials>.  
  
    - Alle im Diagramm enthaltenen Eigenschaften geben Instanzen von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> zurück.  
  
    - Von der <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A>-Methode wird eine Instanz von `MyClientCredentialsSecurityTokenManager` zurückgegeben.  
  
- `MyClientCredentialsSecurityTokenManager` ist eine benutzerdefinierte Implementierung von <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.  
  
    - Von der <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A>-Methode wird eine Instanz von <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider> zurückgegeben.  
  
 ![Diagramm mit der Verwendung von Clientanmeldeinformationen](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")  
  
 Weitere Informationen zu benutzerdefinierten Anmeldeinformationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Darüber hinaus muss eine Prüfung für die benutzerdefinierte Identität erstellt werden, die dann in einer benutzerdefinierten Bindung mit einem benutzerdefinierten Sicherheitsbindungselement verknüpft werden muss. Des Weiteren müssen anstelle der Standardanmeldeinformationen die benutzerdefinierten Anmeldeinformationen verwendet werden.  
  
 Das folgende Diagramm gibt Aufschluss über die Klassen für die benutzerdefinierte Bindung sowie über die Verknüpfung der Prüfung der benutzerdefinierten Identität. An diesem Prozess sind mehrere Bindungselemente beteiligt, die alle von <xref:System.ServiceModel.Channels.BindingElement> erben. Das <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> besitzt die <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>-Eigenschaft, die eine Instanz von <xref:System.ServiceModel.Security.IdentityVerifier> zurückgibt, von der aus `MyIdentityVerifier` angepasst wird.  
  
 ![Diagramm mit der ein benutzerdefiniertes Bindungselement](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")  
  
 Weitere Informationen zum Erstellen einer benutzerdefinierten identitätsüberprüfung finden Sie unter Vorgehensweise: [Vorgehensweise: Erstellen eine benutzerdefinierten Clientidentitätsüberprüfung](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md).  
  
### <a name="to-use-separate-certificates-for-signing-and-encryption"></a>So verwenden Sie separate Zertifikate für Signieren und Verschlüsselung  
  
1. Definieren Sie eine neue Clientanmeldeinformationen-Klasse, die von der <xref:System.ServiceModel.Description.ClientCredentials>-Klasse erbt. Implementieren Sie vier neue Eigenschaften, um die Angabe mehrerer Zertifikate zu ermöglichen: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` und `ServiceEncryptingCertificate`. Überschreiben Sie auch die <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A>-Methode, damit eine Instanz der im nächsten Schritt eingerichteten benutzerdefinierten <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>-Klasse zurückgegeben wird.  
  
     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]  
  
2. Definieren Sie einen neuen Clientsicherheitstoken-Manager, der von der <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>-Klasse erbt. Überschreiben Sie die <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A>-Methode, um einen entsprechenden Sicherheitstokenanbieter zu erstellen. Der `requirement`-Parameter <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) stellt die Nachrichtenrichtung und die Schlüsselverwendung zur Verfügung.  
  
     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]  
  
3. Definieren Sie eine neue Dienstanmeldeinformationen-Klasse, die von der <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse erbt. Implementieren Sie vier neue Eigenschaften, um die Angabe mehrerer Zertifikate zu ermöglichen: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` und `ServiceEncryptingCertificate`. Überschreiben Sie auch die <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A>-Methode, damit eine Instanz der im nächsten Schritt eingerichteten benutzerdefinierten <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>-Klasse zurückgegeben wird.  
  
     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]  
  
4. Definieren Sie einen neuen Dienstsicherheitstoken-Manager, der von der <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>-Klasse erbt. Überschreiben Sie die <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A>-Methode, um anhand der angegebenen Nachrichtenrichtung und Schlüsselverwendung einen entsprechenden Sicherheitstokenanbieter zu erstellen.  
  
     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]  
  
### <a name="to-use-multiple-certificates-on-the-client"></a>So verwenden Sie mehrere Zertifikate über den Client  
  
1. Erstellen Sie eine benutzerdefinierte Bindung. Das Sicherheitsbindungselement muss im Duplexmodus ausgeführt werden, damit für Anforderungen und Antworten verschiedene Sicherheitstokenanbieter zur Verfügung stehen können. Verwenden Sie dazu einen duplexfähigen Transport oder <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, wie im folgenden Code veranschaulicht. Verknüpfen Sie den angepassten <xref:System.ServiceModel.Security.IdentityVerifier>, der im nächsten Schritt definiert wird, mit dem Sicherheitsbindungselement. Ersetzen Sie die standardmäßigen Clientanmeldeinformationen mit den angepassten Clientanmeldeinformationen, die zuvor erstellt werden.  
  
     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]  
  
2. Definieren Sie einen benutzerdefinierten <xref:System.ServiceModel.Security.IdentityVerifier>. Der Dienst verfügt über mehrere Identitäten, da zum Verschlüsseln der Anforderung und zum Signieren der Antwort verschiedene Zertifikate verwendet werden.  
  
    > [!NOTE]
    >  Im folgenden Beispiel führt die zur Verfügung gestellte benutzerdefinierte Identitätsprüfung zu Demonstrationszwecken keine Überprüfung der Endpunktidentität durch. Dies ist keine empfohlene Vorgehensweise für Produktionscode.  
  
     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]  
  
### <a name="to-use-multiple-certificates-on-the-service"></a>So verwenden Sie mehrere Zertifikate für den Dienst  
  
1. Erstellen Sie eine benutzerdefinierte Bindung. Das Sicherheitsbindungselement muss im Duplexmodus ausgeführt werden, damit für Anforderungen und Antworten verschiedene Sicherheitstokenanbieter zur Verfügung stehen können. Verwenden Sie dazu ebenso wie mit dem Client einen duplexfähigen Transport oder <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>, wie im folgenden Code veranschaulicht. Ersetzen Sie die standardmäßigen Dienstanmeldeinformationen mit den angepassten Dienstanmeldeinformationen, die zuvor erstellt werden.  
  
     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
