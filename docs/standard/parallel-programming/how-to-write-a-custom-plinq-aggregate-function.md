---
title: 'Vorgehensweise: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09e128c98b61ecc4ac673d8c9911f4bac476d521
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988429"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Vorgehensweise: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion
Dieses Beispiel zeigt, wie mit der <xref:System.Linq.ParallelEnumerable.Aggregate%2A>-Methode eine benutzerdefinierte Aggregatfunktion auf eine Quellsequenz angewendet wird.  
  
> [!WARNING]
> Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Standardabweichung einer Sequenz von ganzen Zahlen berechnet.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 In diesem Beispiel wird eine Überladung des Aggregate-Standardabfrageoperators verwendet, der für PLINQ eindeutig ist. Diese Überladung nimmt eine zusätzliche <xref:System.Func%603?displayProperty=nameWithType> als dritten Eingabeparameter an. Dieser Delegat kombiniert die Ergebnisse aller Threads, bevor er die abschließende Berechnung der aggregierten Ergebnisse durchführt. In diesem Beispiel addieren wir die Summen aller Threads.  
  
 Beachten Sie: Wenn ein Lambdaausdruckskörper aus einem einzelnen Ausdruck besteht, ist der Rückgabewert des <xref:System.Func%602?displayProperty=nameWithType>-Delegaten der Wert des Ausdrucks.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
