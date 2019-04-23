---
title: 'Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 37d0e6fae8ad0f3a91f1bead23fb5823fc52d420
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313214"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Vorgehensweise: Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse
Die bevorzugte Methode zum Erstellen eines Windows Communication Foundation (WCF)-Vertrags ist mithilfe einer Schnittstelle. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Eine Alternative besteht darin, eine Klasse zu erstellen und anschließend das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt auf die Klasse anzuwenden und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die einzelnen Methoden in der Klasse, die Teil des Vertrags sind, anzuwenden.  
  
> [!WARNING]
>  `[ServiceContract]` und `[ServiceContractAttribute]` dienen dem gleichen Zweck. Das gleiche gilt für `[OperationContract]` und `[OperationContractAttribute]`. In jedem Fall ist die erste Kurznotation für das Letztere.  
  
 Weitere Informationen zu Dienstverträgen finden Sie unter [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Erstellen eines Windows Communication Foundation-Vertrags mit einer Klasse  
  
1. Erstellen Sie eine neue Klasse, die mit Visual Basic, C#, oder einer beliebigen anderen common Language Runtime-Sprache.  
  
2. Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Klasse an.  
  
3. Erstellen Sie Methoden in der Klasse.  
  
4. Anwenden der <xref:System.ServiceModel.OperationContractAttribute> -Klasse auf jede Methode, die als Teil des öffentlichen WCF-Vertrags verfügbar gemacht werden muss.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Klasse dargestellt, die einen Dienstvertrag definiert.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Die Methoden, auf die die <xref:System.ServiceModel.OperationContractAttribute>-Klasse angewendet wird, verwenden standardmäßig ein Anforderung-Antwort-Nachrichtenmuster. Weitere Informationen zu diesem Nachrichtenmuster finden Sie unter [Vorgehensweise: Erstellen Sie einen Anforderung-Antwort-Vertrag](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Sie können auch andere Nachrichtenmuster erstellen und verwenden, indem Sie die Eigenschaften des Attributs festlegen. Weitere Beispiele finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) und [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
