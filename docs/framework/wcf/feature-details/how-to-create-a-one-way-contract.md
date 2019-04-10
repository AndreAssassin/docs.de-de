---
title: 'Vorgehensweise: Erstellen eines unidirektionalen Vertrags'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
ms.openlocfilehash: cc777da65ce1c0d425404b1cc8d47e8189684a7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337005"
---
# <a name="how-to-create-a-one-way-contract"></a>Vorgehensweise: Erstellen eines unidirektionalen Vertrags
Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen unidirektionalen Vertrag verwenden. Solche Methoden rufen Vorgänge für einen Windows Communication Foundation (WCF)-Dienst von einem Client jedoch erwarten nicht, dass eine Antwort. Dieser Vertragstyp kann verwendet werden, um z.&amp;#160;B. Benachrichtigungen für viele Abonnenten zu veröffentlichen. Sie können unidirektionale Verträge auch beim Erstellen eines Duplexvertrags (bidirektionalen Vertrags) verwenden. Dies ermöglicht eine unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils anderen initiieren können. So wird insbesondere dem Server ermöglicht, unidirektionale Aufrufe an den Client durchzuführen, die der Client als Ereignisse behandeln kann. Ausführliche Informationen zum Angeben von unidirektionalen Methoden finden Sie in der Beschreibung zur <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Methode und zur <xref:System.ServiceModel.OperationContractAttribute>-Klasse.  
  
 Weitere Informationen zum Erstellen einer Clientanwendung für einen Duplexvertrag finden Sie unter [Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung-Antwort-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md). Ein Arbeitsbeispiel finden Sie unter den [unidirektionale](../../../../docs/framework/wcf/samples/one-way.md) Beispiel.  
  
### <a name="to-create-a-one-way-contract"></a>So erstellen Sie einen unidirektionalen Vertrag  
  
1. Erstellen Sie einen Dienstvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle anwenden, die die Methoden definiert, die der Dienst implementieren soll.  
  
2. Geben Sie an, welche Methoden in der Schnittstelle ein Client aufrufen kann, indem Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden anwenden.  
  
3. Definieren Sie die Vorgänge, die keine unidirektionale Ausgabe (keinen Rückgabewert und keine out- oder ref-Parameter) haben dürfen, indem Sie die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` festlegen. Beachten Sie, dass alle Vorgänge mit der <xref:System.ServiceModel.OperationContractAttribute>-Klasse standardmäßig einen Anforderung-Antwort-Vertrag erfüllen, weil die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft standardmäßig `false` lautet. Wenn Sie einen unidirektionalen Vertrag für die Methode definieren möchten, müssen Sie den Wert der Attributeigenschaft folglich explizit auf `true` festlegen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein Vertrag für einen Dienst definiert, der mehrere unidirektionale Methoden besitzt. Alle diese Methoden haben unidirektionale Verträge mit Ausnahme von `Equals`, das standardmäßig auf Anforderung-Antwort festgelegt ist und ein Ergebnis zurückgibt.  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Sitzung](../../../../docs/framework/wcf/samples/session.md)
- [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
