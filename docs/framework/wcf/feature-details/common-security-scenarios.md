---
title: Häufige Sicherheitsszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: af58d6b529fba32380bedb9a892a2b1fd4807d96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857570"
---
# <a name="common-security-scenarios"></a>Häufige Sicherheitsszenarien
Die Themen in diesem Abschnitt katalogisieren eine Anzahl möglicher Client- und Dienstsicherheitskonfigurationen. Die Konfigurationen ändern sich aufgrund verschiedenster Faktoren. Zum Beispiel ob sich ein Dienst oder Client im Intranet befindet oder ob die Sicherheit von Windows oder vom Transport (wie HTTPS) gewährleistet wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Internet: Ungesicherter Client und Dienst](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Ein Beispiel eines öffentlichen, ungesicherten Clients und Diensts.  
  
 [Intranet: Ungesicherter Client und Dienst](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Ein grundlegenden Windows Communication Foundation (WCF)-Dienst entwickelt, um Informationen in einem sicheren privaten Netzwerk zu einer WCF-Anwendung bereitzustellen.  
  
 [Transportsicherheit mit Standardauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 Mit dieser Anwendung können sich Clients anhand einer benutzerdefinierten Authentifizierung anmelden.  
  
 [Transportsicherheit mit Windows-Authentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Zeigt einen von der Windows-Sicherheit gesicherten Client und Dienst.  
  
 [Transportsicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 Dieses Szenario verwendet die Transportsicherheit (wie HTTPS), um Vertraulichkeit und Integrität sicherzustellen.  
  
 [Transportsicherheit mit Zertifikatauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Zeigt einen mit einem Zertifikat gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Zeigt einen Client und-Dienst gesichert durch WCF-nachrichtensicherheit.  
  
 [Nachrichtensicherheit mit einem Benutzernamenclient](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 Der Client ist eine Windows Forms-Anwendung, mit der sich die Clients mithilfe eines Domänenbenutzernamens und -Kennworts anmelden können.  
  
 [Nachrichtensicherheit mit einem Zertifikatclient](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit mit einem Windows-Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Eine Variante des Zertifikatsclients. Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationenaushandlung](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Zeigt einen von einer Kerberos-Domäne gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit gegenseitigen Zertifikaten](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Das Serverzertifikat wird mit der Anwendung verteilt und steht außerhalb des Bereichs zur Verfügung.  
  
 [Nachrichtensicherheit durch ausgestellte Token](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 Verbundsicherheit, die Vertrauenswürdigkeit zwischen unabhängigen Domänen ermöglicht.  
  
 [Vertrauenswürdiges Subsystem](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden. Die Webdienste greifen auf zusätzliche Ressourcen (z. B. Datenbanken oder andere Webdienste) zu, die gesichert werden müssen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheitsleitfaden und bewährte Methoden](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
