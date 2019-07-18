---
title: Verwenden von Verträgen im Workflow
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: dc2d631d8a9e588645dd60495c54799b2a2dd8a0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637740"
---
# <a name="using-contracts-in-workflow"></a>Verwenden von Verträgen im Workflow
Beim Implementieren eines Diensts definieren Sie eine Reihe von Verträgen, in denen der Dienst und die von ihm gesendeten und empfangenen Daten beschrieben werden. Die Daten werden als Datenverträge und Nachrichtenverträge dargestellt; sowohl WCF und Workflowdiensten verwenden Datenvertrags- und nachrichtenvertragsdefinitionen als Teil Ihrer dienstbeschreibungen. Der Dienst selbst macht Metadaten (im WSDL-Format) verfügbar, um die Vorgänge des Diensts zu beschreiben. Bei WCF definieren Dienst- und Vorgangsverträge den Dienst und seine unterstützten Vorgänge. In einem Workflowdienst sind diese Verträge jedoch Teil des eigentlichen Geschäftsprozesses. Sie werden in den Metadaten von einem Prozess verfügbar gemacht, der als Vertragsrückschluss bezeichnet wird.  
  
## <a name="contract-inference"></a>Vertragsrückschluss  
 Wenn ein Workflowdienst mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, wird die Workflowdefinition untersucht, und basierend auf den im Workflow gefundenen Messagingaktivitäten wird ein Vertrag generiert. Zum Generieren des Vertrags werden insbesondere die folgenden Aktivitäten und Eigenschaften verwendet:  
  
 <xref:System.ServiceModel.Activities.Receive>-Aktivität  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <xref:System.ServiceModel.Activities.SendReply>-Aktivität  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität  
  
 Das Endergebnis des Vertragsrückschlusses ist eine Beschreibung des Diensts, bei der die gleichen Datenstrukturen wie für WCF-Dienstverträge und -Vorgangsverträge verwendet werden. Diese Informationen werden dann verwendet, um WSDL für den Workflowdienst verfügbar zu machen.  
  
## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
- [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Vorgehensweise: Erstellen eines Workflowdiensts, das Verarbeiten eines vorhandenen Dienstvertrags](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
