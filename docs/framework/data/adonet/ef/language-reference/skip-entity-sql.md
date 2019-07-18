---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 88d4c9c987f451e9a653d5b9c213e7158670ed4b
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662139"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)
Physisches Paging kann mithilfe der SKIP-Unterklausel in der ORDER BY-Klausel durchgeführt werden. SKIP kann nicht ohne die ORDER BY-Klausel verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Argumente  
 `n`  
 Die Anzahl zu überspringender Elemente.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine ORDER BY-Klausel den Ausdruck SKIP als Unterklausel enthält, werden die Ergebnisse den Sortierangaben entsprechend sortiert, und das Resultset enthält die Zeilen, die auf den SKIP-Ausdruck folgen. Mit SKIP 5 werden beispielsweise die ersten fünf Zeilen übersprungen und nur die Zeilen ab der sechsten Zeile zurückgegeben.  
  
> [!NOTE]
>  Eine [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage ist ungültig, wenn im selben Abfrageausdruck sowohl ein TOP-Modifizierer als auch eine SKIP-Unterklausel vorhanden sind. In der Abfrage sollte der TOP-Ausdruck in einen LIMIT-Ausdruck geändert werden.  
  
> [!NOTE]
>  In SQL Server 2000 möglicherweise die Verwendung von SKIP mit ORDER BY auf Nichtschlüsselspalten falsche Ergebnisse zurück. Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält. Dies liegt an der Übersetzung von SKIP für SQL Server 2000. Im folgenden Code können beispielsweise mehr als fünf Zeilen übersprungen werden, wenn `E.NonKeyColumn` Werte doppelt enthält:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 Die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage im [Vorgehensweise: Seite über Abfrageergebnisse](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) den ORDER BY-Operator mit SKIP verwendet, um die in einer SELECT-Anweisung zurückgegebenen Objekte zu verwendende Sortierreihenfolge anzugeben.  
  
## <a name="see-also"></a>Siehe auch

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Vorgehensweise: Seitenweise Abfrageresultate durch Navigieren](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
