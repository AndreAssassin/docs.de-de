---
title: Kryptografische Flexibilität in WCF-Sicherheit
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: b8e3b6dc62baf31901520d7f5edac0529e937016
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490941"
---
# <a name="cryptographic-agility-in-wcf-security"></a>Kryptografische Flexibilität in WCF-Sicherheit

Dieses Beispiel zeigt, wie ein Standard-/benutzerdefinierter Algorithmus eine agile kryptografieimplementierung in einem Windows Communication Foundation (WCF)-Client und Dienst bereitstellen. Das Beispiel besteht aus den folgenden Projekten:

**Dienst**

Dies ist eine selbst gehostete WCF-Dienst, der implementiert die `ICalculator` Schnittstelle und sichert den Endpunkt mithilfe der <xref:System.ServiceModel.WSHttpBinding> mit sicheren Sitzung und zuverlässige Sitzung deaktiviert. Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.

**Client**

Dies ist ein WCF-Client, der nach der erfolgreichen Authentifizierung auf den Dienst zugreift. Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden. Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.

## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie die Cryptoagility-Projektmappe in Visual Studio 2012.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Öffnen Sie den Datei-Explorer, navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Service\bin, und führen Sie die service.exe-Datei mit Administratorberechtigungen aus, indem Sie mit der rechten Maustaste service.exe und auswählen **als Administrator ausführen**.

4. Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a>Siehe auch

- [Windows Communication Foundation-Sicherheit](../feature-details/security.md)
