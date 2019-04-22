---
title: Abfrageausdruckssyntax für Standardabfrageoperatoren (Visual Basic)
ms.date: 07/20/2015
ms.assetid: eb978d86-d3b5-497b-95ce-a054bea8f510
ms.openlocfilehash: bdbca93d5898e363ccf62b13231163573e2ba972
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832514"
---
# <a name="query-expression-syntax-for-standard-query-operators-visual-basic"></a>Abfrageausdruckssyntax für Standardabfrageoperatoren (Visual Basic)
Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von Visual Basic, die ihnen ermöglicht, die als Teil des aufzurufenden eine *Abfrageausdruck*. Mit einem Abfrageausdruck kann eine Abfrage besser lesbar ausgedrückt werden als mit dessen *methodenbasierter* Entsprechung. Die Abfrageausdrucksklauseln werden bei der Kompilierung in Aufrufe der Abfragemethoden übersetzt.  
  
## <a name="query-expression-syntax-table"></a>Tabelle: Abfrageausdruckssyntax  
 In der folgenden Tabelle finden Sie eine Liste von Standardabfrageoperatoren, die über äquivalente Abfrageausdrucksklauseln verfügen.  
  
|Methode|Visual Basic-Abfrageausdruckssyntax|  
|------------|------------------------------------------|  
|<xref:System.Linq.Enumerable.All%2A>|`Aggregate … In … Into All(…)`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Any%2A>|`Aggregate … In … Into Any()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Average%2A>|`Aggregate … In … Into Average()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Cast%2A>|`From … As …`<br /><br /> (Weitere Informationen finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Count%2A>|`Aggregate … In … Into Count()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Distinct%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|`Distinct`<br /><br /> (Weitere Informationen finden Sie unter [Distinct-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`Group … By … Into …`<br /><br /> (Weitere Informationen finden Sie unter [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`Group Join … In … On …`<br /><br /> (Weitere Informationen finden Sie unter [Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`From x In …, y In … Where x.a = b.a`<br /><br /> - oder - <br /><br /> `Join … [As …]In … On …`<br /><br /> (Weitere Informationen finden Sie unter [Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md).)|  
|<xref:System.Linq.Enumerable.LongCount%2A>|`Aggregate … In … Into LongCount()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Max%2A>|`Aggregate … In … Into Max()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Min%2A>|`Aggregate … In … Into Min()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By … Descending`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`Select`<br /><br /> (Weitere Informationen finden Sie unter [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Mehrere `From` Klauseln<br /><br /> (Weitere Informationen finden Sie unter [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md).)|  
|<xref:System.Linq.Enumerable.Skip%2A>|`Skip`<br /><br /> (Weitere Informationen finden Sie unter [Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md).)|  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|`Skip While`<br /><br /> (Weitere Informationen finden Sie unter [Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md).)|  
|<xref:System.Linq.Enumerable.Sum%2A>|`Aggregate … In … Into Sum()`<br /><br /> (Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).)|  
|<xref:System.Linq.Enumerable.Take%2A>|`Take`<br /><br /> (Weitere Informationen finden Sie unter [Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md).)|  
|<xref:System.Linq.Enumerable.TakeWhile%2A>|`Take While`<br /><br /> (Weitere Informationen finden Sie unter [dauern While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, …`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`Order By …, … Descending`<br /><br /> (Weitere Informationen finden Sie unter [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`Where`<br /><br /> (Weitere Informationen finden Sie unter [Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md).)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
