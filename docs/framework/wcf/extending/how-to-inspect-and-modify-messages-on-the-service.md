---
title: 'Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 1356983361c483170d9d7365932b788f2421bf09
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795605"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst
Sie können die eingehenden oder ausgehenden Nachrichten über einen Windows Communication Foundation (WCF)-Client überprüfen <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> oder ändern, indem Sie einen implementieren und ihn in die Dienst Laufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Dispatchern](extending-dispatchers.md). Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1. Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2. Implementieren Sie eine <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>-, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>- oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Schnittstelle, je nach dem Umfang, in dem Sie Ihren Dienstnachrichteninspektor auf einfache Weise einfügen möchten.  
  
3. Fügen Sie Ihr Verhalten ein, bevor Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode auf dem <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> aufrufen. Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
- Eine Dienstinspektorimplementierung.  
  
- Ein Dienstverhalten, das den Inspektor einfügt.  
  
- Eine Konfigurationsdatei, die das Verhalten lädt und in einer Dienstanwendung ausführt.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md)
