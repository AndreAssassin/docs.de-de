---
title: 'Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 472304dff23e92620dd461e8bc43c3093431ddc4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962518"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage
Das folgende Beispiel zeigt, wie Sie eine einfache Parallel LINQ-Abfrage erstellen, indem Sie die <xref:System.Linq.ParallelEnumerable.AsParallel%2A>-Erweiterungsmethode in der Quellsequenz verwenden und die Abfrage mit der <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Methode ausführen.  
  
> [!NOTE]
> In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 Dieses Beispiel zeigt das grundlegende Muster zum Erstellen und Ausführen einer beliebigen Parallel LINQ-Abfrage, wenn die Sortierung der Ergebnissequenz nicht wichtig ist. Unsortierte Abfragen sind im Allgemeinen schneller als sortierte Abfragen. Die Abfrage partitioniert die Quelle in Aufgaben, die asynchron in mehreren Threads ausgeführt werden. Die Reihenfolge, in der jede Aufgabe abgeschlossen wird, hängt nicht nur von der Menge der mit der Verarbeitung der Elemente in der Partition verbundenen Arbeit, sondern auch von externen Faktoren ab, beispielsweise wie das Betriebssystem jeden Thread plant. Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md). Weitere Informationen zur Beibehaltung der Sortierung von Elementen in einer Abfrage finden Sie unter [Vorgehensweise: Steuern der Reihenfolge in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
