---
title: 'Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrincipalPermissionAttribute class
- WCF, authorization
- WCF, security
ms.assetid: 5162f5c4-8781-4cc4-9425-bb7620eaeaf4
ms.openlocfilehash: ae2aa4c5629096ee7d888e7c4e334c3b6696db3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929089"
---
# <a name="how-to-restrict-access-with-the-principalpermissionattribute-class"></a>Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse
Den Zugriff auf Ressourcen auf einem Windows-Domänencomputer zu kontrollieren gehört zu den grundlegenden Sicherheitsaufgaben. So sollten zum Beispiel nur bestimmte Benutzer vertrauliche Daten wie Lohnlisten anzeigen können. In diesem Thema wird erklärt, wie Sie den Zugriff auf eine Methode beschränken können, indem Sie es zur Voraussetzung machen, dass die entsprechenden Benutzer einer vordefinierten Gruppe angehören. Ein Arbeitsbeispiel finden Sie unter [Zugriff auf Dienstvorgänge autorisieren](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md).  
  
 Diese Aufgabe umfasst zwei separate Schritte. Zuerst wird die Gruppe erstellt und mit Benutzern gefüllt. Anschließend wird in einem zweiten Schritt die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse angewendet, um die Gruppe anzugeben.  
  
### <a name="to-create-a-windows-group"></a>So erstellen Sie eine Windows-Gruppe  
  
1. Öffnen der **Computerverwaltung** Konsole.  
  
2. Klicken Sie im linken Bereich auf **lokale Benutzer und Gruppen**.  
  
3. Mit der rechten Maustaste **Gruppen**, und klicken Sie auf **neue Gruppe**.  
  
4. In der **Gruppenname** geben einen Namen für die neue Gruppe.  
  
5. In der **Beschreibung** geben eine Beschreibung der neuen Gruppe.  
  
6. Klicken Sie auf die **hinzufügen** Schaltfläche, um neue Mitglieder zur Gruppe hinzuzufügen.  
  
7. Falls Sie sich selbst zur Gruppe hinzugefügt haben und den folgenden Code testen möchten, müssen Sie sich vom Computer abmelden und dann wieder anmelden, damit Sie in die Gruppe aufgenommen werden.  
  
### <a name="to-demand-user-membership"></a>So fordern Sie die Benutzermitgliedschaft an  
  
1. Öffnen Sie die Windows Communication Foundation (WCF)-Codedatei, die den implementierten dienstvertragscode enthält. Weitere Informationen zum Implementieren eines Vertrags finden Sie unter [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
2. Wenden Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut auf jede Methode an, die nur für eine bestimmte Gruppe zugelassen werden soll. Legen Sie für die <xref:System.Security.Permissions.SecurityAttribute.Action%2A>-Eigenschaft den Wert <xref:System.Security.Permissions.SecurityAction.Demand> fest, und setzen Sie die <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>-Eigenschaft auf den Namen der Gruppe. Zum Beispiel:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#1)]
     [!code-vb[c_PrincipalPermissionAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#1)]  
  
    > [!NOTE]
    >  Wenn Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Attribut auf einen Vertrag anwenden, wird eine <xref:System.Security.SecurityException> ausgelöst. Das Attribut kann nur auf Methodenebene angewendet werden.  
  
## <a name="using-a-certificate-to-control-access-to-a-method"></a>Steuern des Zugriffs auf eine Methode mithilfe eines Zertifikats  
 Sie können mit der `PrincipalPermissionAttribute`-Klasse auch dann den Zugriff auf eine Methode steuern, wenn es sich bei den Clientanmeldeinformationen um ein Zertifikat handelt. Hierfür müssen Sie den Antragsteller und den Fingerabdruck des Zertifikats kennen.  
  
 Um ein Zertifikat für seine Eigenschaften untersuchen zu können, finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md). Der Fingerabdruckwert finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
#### <a name="to-control-access-using-a-certificate"></a>So steuern Sie den Zugriff mithilfe eines Zertifikats  
  
1. Wenden Sie die <xref:System.Security.Permissions.PrincipalPermissionAttribute>-Klasse auf die Methode an, für die der Zugriff eingeschränkt werden soll.  
  
2. Setzen Sie die Aktion des Attributs auf <xref:System.Security.Permissions.SecurityAction.Demand?displayProperty=nameWithType>.  
  
3. Verwenden Sie für die `Name`-Eigenschaft eine Zeichenfolge mit dem Antragstellernamen und dem Fingerabdruck des Zertifikats. Trennen Sie die beiden Werte durch ein Semikolon und ein Leerzeichen, wie im folgenden Beispiel gezeigt:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#2)]
     [!code-vb[c_PrincipalPermissionAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#2)]  
  
4. Legen Sie für die <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>-Eigenschaft den Wert <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> wie im folgenden Konfigurationsbeispiel gezeigt fest:  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="SvcBehavior1">  
      <serviceAuthorization principalPermissionMode="UseAspNetRoles" />  
      </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Durch den Wert `UseAspNetRoles` wird angegeben, dass mit der `Name`-Eigenschaft von `PrincipalPermissionAttribute` ein Zeichenfolgenvergleich durchgeführt wird. Wenn ein Zertifikat als Clientanmeldeinformationen verwendet wird, verkettet werden standardmäßig WCF allgemeinen Namen des Zertifikats und den Fingerabdruck durch ein Semikolon, um einen eindeutigen Wert für die primäre Identität des Clients zu erstellen. Sofern für den Dienst `UseAspNetRoles` als `PrincipalPermissionMode` gewählt wurde, wird dieser Wert für die primäre Identität mit dem Wert der `Name`-Eigenschaft verglichen, um die Zugriffsrechte des Benutzers zu ermitteln.  
  
     Sie können alternativ wie im folgenden Beispiel auch die <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>-Eigenschaft im Code festlegen, wenn Sie einen selbst gehosteten Dienst erstellen:  
  
     [!code-csharp[c_PrincipalPermissionAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#3)]
     [!code-vb[c_PrincipalPermissionAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- <xref:System.Security.Permissions.SecurityAction.Demand>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute.Role%2A>
- [Zugriffsautorisierung für Dienstvorgänge](../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [Übersicht über die Sicherheit](../../../docs/framework/wcf/feature-details/security-overview.md)
- [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
