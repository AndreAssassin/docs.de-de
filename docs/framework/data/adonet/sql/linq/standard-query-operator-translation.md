---
title: Übersetzen von Standardabfrageoperatoren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: 4df1653b7bd6865ad9f5d7d3fb9be6815dcfe018
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781015"
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="34caa-102">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="34caa-102">Standard Query Operator Translation</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-103">übersetzt Standardabfrageoperatoren in SQL-Befehle.</span><span class="sxs-lookup"><span data-stu-id="34caa-103">translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="34caa-104">Der Abfrage Prozessor der Datenbank bestimmt die Ausführungs Semantik der SQL-Übersetzung.</span><span class="sxs-lookup"><span data-stu-id="34caa-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>

<span data-ttu-id="34caa-105">Standard Abfrage Operatoren werden für *Sequenzen*definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="34caa-106">Eine Sequenz wird *geordnet* und basiert auf der Verweis Identität für jedes Element der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="34caa-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="34caa-107">Weitere Informationen finden Sie unter [Übersicht über Standard Abfrage Operatoren (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) oder unter [Übersicht über Standard Abfrage Operatoren (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="34caa-107">For more information, see [Standard Query Operators Overview (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

<span data-ttu-id="34caa-108">SQL behandelt hauptsächlich *ungeordnete Sätze von Werten*.</span><span class="sxs-lookup"><span data-stu-id="34caa-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="34caa-109">Die Sortierung ist in der Regel ein explizit angegebener, nachgelagerter Prozess, der auf das Endergebnis einer Abfrage und nicht auf Zwischenergebnisse angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="34caa-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="34caa-110">Die Identität wird durch Werte definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-110">Identity is defined by values.</span></span> <span data-ttu-id="34caa-111">Aus diesem Grund werden SQL-Abfragen für die Handhabung von Multisets (*Taschen*) anstelle von *Sätzen*verstanden.</span><span class="sxs-lookup"><span data-stu-id="34caa-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>

<span data-ttu-id="34caa-112">Die folgenden Abschnitte beschreiben die Unterschiede zwischen den Standardabfrageoperatoren und ihrer SQL-Übersetzung für den SQL Server-Anbieter in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34caa-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

## <a name="operator-support"></a><span data-ttu-id="34caa-113">Operatorunterstützung</span><span class="sxs-lookup"><span data-stu-id="34caa-113">Operator Support</span></span>

### <a name="concat"></a><span data-ttu-id="34caa-114">Concat</span><span class="sxs-lookup"><span data-stu-id="34caa-114">Concat</span></span>

<span data-ttu-id="34caa-115">Die <xref:System.Linq.Enumerable.Concat%2A>-Methode ist für geordnete Multisets definiert, bei denen die Reihenfolge des Empfängers und des Arguments identisch ist.</span><span class="sxs-lookup"><span data-stu-id="34caa-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="34caa-116"><xref:System.Linq.Enumerable.Concat%2A> fungiert als `UNION ALL` für die Multisets, gefolgt von der allgemeinen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="34caa-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>

<span data-ttu-id="34caa-117">Die Sortierung in SQL ist der letzte Schritt vor dem Erzeugen von Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="34caa-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="34caa-118"><xref:System.Linq.Enumerable.Concat%2A> behält die Reihenfolge der Argumente nicht bei.</span><span class="sxs-lookup"><span data-stu-id="34caa-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="34caa-119">Um die entsprechende Sortierung sicherzustellen, müssen Sie die Ergebnisse von <xref:System.Linq.Enumerable.Concat%2A> explizit sortieren.</span><span class="sxs-lookup"><span data-stu-id="34caa-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>

### <a name="intersect-except-union"></a><span data-ttu-id="34caa-120">Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="34caa-120">Intersect, Except, Union</span></span>

<span data-ttu-id="34caa-121">Die <xref:System.Linq.Enumerable.Intersect%2A>-Methode und die <xref:System.Linq.Enumerable.Except%2A>-Methode sind nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="34caa-122">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-122">The semantics for multisets is undefined.</span></span>

<span data-ttu-id="34caa-123">Die <xref:System.Linq.Enumerable.Union%2A>-Methode ist für Multisets definiert, und zwar als unsortierte Verkettung der Multisets (effektiv als Ergebnis der UNION ALL-Klausel in SQL).</span><span class="sxs-lookup"><span data-stu-id="34caa-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>

### <a name="take-skip"></a><span data-ttu-id="34caa-124">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="34caa-124">Take, Skip</span></span>

<span data-ttu-id="34caa-125"><xref:System.Linq.Enumerable.Take%2A>die <xref:System.Linq.Enumerable.Skip%2A> -Methode und die-Methode sind nur für *geordnete Sätze*gut definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="34caa-126">Die Semantik für ungeordnete Sätze oder Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-126">The semantics for unordered sets or multisets are undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="34caa-127"><xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> weisen bestimmte Einschränkungen auf, wenn sie für Abfragen in SQL Server 2000 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="34caa-128">Weitere Informationen finden Sie im Eintrag "überspringen und Entfernen von Ausnahmen in SQL Server 2000" in der [Problem](troubleshooting.md)Behandlung.</span><span class="sxs-lookup"><span data-stu-id="34caa-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

<span data-ttu-id="34caa-129">Aufgrund von Einschränkungen bei der Reihenfolge in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL versucht, die Reihenfolge des Arguments dieser Methoden auf das Ergebnis der-Methode zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="34caa-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="34caa-130">Betrachten Sie z. B. die folgende [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage:</span><span class="sxs-lookup"><span data-stu-id="34caa-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

<span data-ttu-id="34caa-131">Das generierte SQL für diesen Code verschiebt die Sortierung wie folgt ans Ende:</span><span class="sxs-lookup"><span data-stu-id="34caa-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

<span data-ttu-id="34caa-132">Es ist offensichtlich, dass die angegebene Sortierung konsistent sein muss, wenn <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="34caa-133">Andernfalls sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-133">Otherwise, the results are undefined.</span></span>

<span data-ttu-id="34caa-134"><xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> sind für nicht negative, konstante Integralargumente auf der Basis der Spezifikation für Standardabfrageoperatoren gut definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>

### <a name="operators-with-no-translation"></a><span data-ttu-id="34caa-135">Operatoren ohne Übersetzung</span><span class="sxs-lookup"><span data-stu-id="34caa-135">Operators with No Translation</span></span>

<span data-ttu-id="34caa-136">Die folgenden Methoden werden nicht von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="34caa-137">Der einfachste Grund ist der Unterschied zwischen ungeordneten Multisets und Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="34caa-137">The most common reason is the difference between unordered multisets and sequences.</span></span>

|<span data-ttu-id="34caa-138">Operatoren</span><span class="sxs-lookup"><span data-stu-id="34caa-138">Operators</span></span>|<span data-ttu-id="34caa-139">Begründung</span><span class="sxs-lookup"><span data-stu-id="34caa-139">Rationale</span></span>|
|---------------|---------------|
|<span data-ttu-id="34caa-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="34caa-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="34caa-141">SQL-Abfragen verwenden Multisets, keine Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="34caa-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="34caa-142">`ORDER BY` muss die letzte Klausel sein, die auf die Ergebnisse angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="34caa-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="34caa-143">Aus diesem Grund gibt es keine allgemeine Übersetzung dieser beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="34caa-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="34caa-144">Die Übersetzung dieser Methode ist für eine geordnete Menge möglich. Sie wird jedoch derzeit von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="34caa-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="34caa-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="34caa-146">Die Übersetzung dieser Methoden ist für eine geordnete Menge möglich. Sie werden jedoch derzeit von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="34caa-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="34caa-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="34caa-148">SQL-Abfragen verwenden Multisets, keine indizierbaren Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="34caa-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|
|<span data-ttu-id="34caa-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (Überladung mit Standard-arg)</span><span class="sxs-lookup"><span data-stu-id="34caa-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="34caa-150">Im Allgemeinen kann ein Standardwert nicht für ein beliebiges Tupel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="34caa-151">NULL-Werte für Tupel sind in einigen Fällen durch äußere Joins möglich.</span><span class="sxs-lookup"><span data-stu-id="34caa-151">Null values for tuples are possible in some cases through outer joins.</span></span>|

## <a name="expression-translation"></a><span data-ttu-id="34caa-152">Ausdrucksübersetzung</span><span class="sxs-lookup"><span data-stu-id="34caa-152">Expression Translation</span></span>

### <a name="null-semantics"></a><span data-ttu-id="34caa-153">NULL-Semantik</span><span class="sxs-lookup"><span data-stu-id="34caa-153">Null semantics</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-154">wendet keine NULL-Vergleichssemantik auf SQL an.</span><span class="sxs-lookup"><span data-stu-id="34caa-154">does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="34caa-155">Vergleichsoperatoren werden syntaktisch zu ihren SQL-Entsprechungen übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="34caa-156">Aus diesem Grund reflektiert die Semantik SQL-Semantik, die von Server- oder Verbindungseinstellungen definiert wird.</span><span class="sxs-lookup"><span data-stu-id="34caa-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="34caa-157">Beispielsweise werden zwei NULL-Werte unter den Standard SQL Server Einstellungen als ungleich betrachtet, Sie können jedoch die Einstellungen ändern, um die Semantik zu ändern.</span><span class="sxs-lookup"><span data-stu-id="34caa-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-158">zieht beim Übersetzen von Abfragen keine Servereinstellungen in Betracht.</span><span class="sxs-lookup"><span data-stu-id="34caa-158">does not consider server settings when it translates queries.</span></span>

<span data-ttu-id="34caa-159">Ein Vergleich mit dem NULL-Literal wird in die entsprechende SQL-Version (`is null` oder `is not null`) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="34caa-160">Der Wert von `null` in der Zusammenstellung wird von SQL-Server definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-161">ändert die Zusammenstellung nicht.</span><span class="sxs-lookup"><span data-stu-id="34caa-161">does not change the collation.</span></span>

### <a name="aggregates"></a><span data-ttu-id="34caa-162">Aggregate</span><span class="sxs-lookup"><span data-stu-id="34caa-162">Aggregates</span></span>

<span data-ttu-id="34caa-163">Die Aggregationsmethode für Standardabfrageoperatoren <xref:System.Linq.Enumerable.Sum%2A> ergibt bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz 0.</span><span class="sxs-lookup"><span data-stu-id="34caa-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="34caa-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]bleibt die Semantik von SQL unverändert, und <xref:System.Linq.Enumerable.Sum%2A> für eine leere Sequenz `null` oder eine Sequenz, die nur Nullen enthält, wird anstelle von NULL ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="34caa-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>

<span data-ttu-id="34caa-165">SQL-Einschränkungen für Zwischenergebnisse gelten in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für Summen.</span><span class="sxs-lookup"><span data-stu-id="34caa-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="34caa-166">Die <xref:System.Linq.Enumerable.Sum%2A> von 32-Bit-Ganzzahlmengen wird nicht berechnet, indem man 64-Bit-Ergebnisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="34caa-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="34caa-167">Bei einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Übersetzung von <xref:System.Linq.Enumerable.Sum%2A> kann es zu einem Überlauf kommen, auch wenn die Implementierung von Standardabfrageoperatoren bei der entsprechenden Sequenz im Arbeitsspeicher keinen Überlauf verursacht.</span><span class="sxs-lookup"><span data-stu-id="34caa-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>

<span data-ttu-id="34caa-168">In gleicher Weise wird die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Übersetzung von <xref:System.Linq.Enumerable.Average%2A> zu Ganzzahlen als `integer` und nicht als `double` übersetzt.</span><span class="sxs-lookup"><span data-stu-id="34caa-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>

### <a name="entity-arguments"></a><span data-ttu-id="34caa-169">Entitätsargumente</span><span class="sxs-lookup"><span data-stu-id="34caa-169">Entity Arguments</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="34caa-170">ermöglicht die Verwendung von Entitäts Typen in <xref:System.Linq.Enumerable.GroupBy%2A> der <xref:System.Linq.Enumerable.OrderBy%2A> -Methode und der-Methode.</span><span class="sxs-lookup"><span data-stu-id="34caa-170">enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="34caa-171">In der Übersetzung dieser Operatoren gilt die Verwendung eines Arguments als Entsprechung zur Angabe aller Member dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="34caa-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="34caa-172">Der folgende Code ist z. B. äquivalent:</span><span class="sxs-lookup"><span data-stu-id="34caa-172">For example, the following code is equivalent:</span></span>

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a><span data-ttu-id="34caa-173">Gleichwertige/vergleichbare Argumente</span><span class="sxs-lookup"><span data-stu-id="34caa-173">Equatable / Comparable Arguments</span></span>

<span data-ttu-id="34caa-174">Die Gleichheit von Argumenten ist in der Implementierung der folgenden Methoden erforderlich:</span><span class="sxs-lookup"><span data-stu-id="34caa-174">Equality of arguments is required in the implementation of the following methods:</span></span>

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="34caa-175">unterstützt Gleichheit und Vergleich für *flache* Argumente, jedoch nicht für Argumente, die Sequenzen sind oder enthalten.</span><span class="sxs-lookup"><span data-stu-id="34caa-175">supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="34caa-176">Ein flaches Argument ist ein Typ, der einer SQL-Zeile zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="34caa-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="34caa-177">Eine Projektion von einem oder mehreren statisch festgelegten Entitätstypen ohne Sequenz gilt als flaches Argument.</span><span class="sxs-lookup"><span data-stu-id="34caa-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>

<span data-ttu-id="34caa-178">Es folgen Beispiele für flache Argumente:</span><span class="sxs-lookup"><span data-stu-id="34caa-178">Following are examples of flat arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

<span data-ttu-id="34caa-179">Es folgen Beispiele für nicht flache (hierarchische) Argumente.</span><span class="sxs-lookup"><span data-stu-id="34caa-179">The following are examples of non-flat (hierarchical) arguments.</span></span>

[!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a><span data-ttu-id="34caa-180">Visual Basic-Funktionsübersetzung</span><span class="sxs-lookup"><span data-stu-id="34caa-180">Visual Basic Function Translation</span></span>

<span data-ttu-id="34caa-181">Die folgenden, vom Visual Basic-Compiler verwendeten Hilfsfunktionen werden in entsprechende SQL-Operatoren und -Funktionen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="34caa-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

<span data-ttu-id="34caa-182">Konvertierungsmethoden:</span><span class="sxs-lookup"><span data-stu-id="34caa-182">Conversion methods:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="34caa-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="34caa-183">ToBoolean</span></span>|<span data-ttu-id="34caa-184">ToSByte</span><span class="sxs-lookup"><span data-stu-id="34caa-184">ToSByte</span></span>|<span data-ttu-id="34caa-185">ToByte</span><span class="sxs-lookup"><span data-stu-id="34caa-185">ToByte</span></span>|<span data-ttu-id="34caa-186">ToChar</span><span class="sxs-lookup"><span data-stu-id="34caa-186">ToChar</span></span>|
|<span data-ttu-id="34caa-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="34caa-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="34caa-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="34caa-188">ToDate</span></span>|<span data-ttu-id="34caa-189">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="34caa-189">ToDecimal</span></span>|<span data-ttu-id="34caa-190">ToDouble</span><span class="sxs-lookup"><span data-stu-id="34caa-190">ToDouble</span></span>|
|<span data-ttu-id="34caa-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="34caa-191">ToInteger</span></span>|<span data-ttu-id="34caa-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="34caa-192">ToUInteger</span></span>|<span data-ttu-id="34caa-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="34caa-193">ToLong</span></span>|<span data-ttu-id="34caa-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="34caa-194">ToULong</span></span>|
|<span data-ttu-id="34caa-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="34caa-195">ToShort</span></span>|<span data-ttu-id="34caa-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="34caa-196">ToUShort</span></span>|<span data-ttu-id="34caa-197">ToSingle</span><span class="sxs-lookup"><span data-stu-id="34caa-197">ToSingle</span></span>|<span data-ttu-id="34caa-198">ToString</span><span class="sxs-lookup"><span data-stu-id="34caa-198">ToString</span></span>|

## <a name="inheritance-support"></a><span data-ttu-id="34caa-199">Unterstützung von Vererbung</span><span class="sxs-lookup"><span data-stu-id="34caa-199">Inheritance Support</span></span>

### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="34caa-200">Einschränkungen der Vererbungszuordnung</span><span class="sxs-lookup"><span data-stu-id="34caa-200">Inheritance Mapping Restrictions</span></span>

<span data-ttu-id="34caa-201">Weitere Informationen finden Sie unter [Vorgehensweise: Zuordnen von Vererbungs Hierarchien](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="34caa-201">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>

### <a name="inheritance-in-queries"></a><span data-ttu-id="34caa-202">Vererbung in Abfragen</span><span class="sxs-lookup"><span data-stu-id="34caa-202">Inheritance in Queries</span></span>

<span data-ttu-id="34caa-203">C#-Umwandlungen werden nur in Projektionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34caa-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="34caa-204">An anderer Stelle verwendete Umwandlungen werden nicht übersetzt, sonder ignoriert.</span><span class="sxs-lookup"><span data-stu-id="34caa-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="34caa-205">Neben den SQL-Funktionsnamen führt SQL tatsächlich nur das Äquivalent von Common Language Runtime (CLR) <xref:System.Convert> aus.</span><span class="sxs-lookup"><span data-stu-id="34caa-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="34caa-206">Das heißt, SQL kann den Wert eines Typs ändern.</span><span class="sxs-lookup"><span data-stu-id="34caa-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="34caa-207">Es gibt keine Entsprechung zu CLR-Umwandlungen, da es kein Konzept für die Neuinterpretation der gleichen Bits als die eines anderen Typs gibt.</span><span class="sxs-lookup"><span data-stu-id="34caa-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="34caa-208">Aus diesem Grund funktioniert eine C#-Umwandlung nur lokal.</span><span class="sxs-lookup"><span data-stu-id="34caa-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="34caa-209">Eine Remoteausführung ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="34caa-209">It is not remoted.</span></span>

<span data-ttu-id="34caa-210">Der `is`-Operator und der `as`-Operator sowie die `GetType`-Methode werden nicht auf den `Select`-Operator beschränkt.</span><span class="sxs-lookup"><span data-stu-id="34caa-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="34caa-211">Sie können auch in anderen Abfrageoperatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-211">They can be used in other query operators also.</span></span>

## <a name="sql-server-2008-support"></a><span data-ttu-id="34caa-212">SQL Server 2008-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34caa-212">SQL Server 2008 Support</span></span>

<span data-ttu-id="34caa-213">Ab .NET Framework 3.5 SP1 unterstützt LINQ to SQL das Mapping zu den in SQL Server 2008 neu eingeführten Datums- und Uhrzeittypen.</span><span class="sxs-lookup"><span data-stu-id="34caa-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="34caa-214">Einschränkungen bestehen jedoch für die LINQ to SQL-Abfrageoperatoren, die beim Arbeiten mit den diesen neuen Typen zugeordneten Werten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="34caa-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>

### <a name="unsupported-query-operators"></a><span data-ttu-id="34caa-215">Nicht unterstützte Abfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="34caa-215">Unsupported Query Operators</span></span>

<span data-ttu-id="34caa-216">Die folgenden Abfrageoperatoren werden nicht für Werte unterstützt, die den neuen Datums- und Uhrzeittypen von SQL Server zugeordnet sind: `DATETIME2`, `DATE`, `TIME` und `DATETIMEOFFSET`.</span><span class="sxs-lookup"><span data-stu-id="34caa-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

<span data-ttu-id="34caa-217">Weitere Informationen über das Mapping zu diesen SQL Server Datums-und Uhrzeit Typen finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="34caa-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>

## <a name="sql-server-2005-support"></a><span data-ttu-id="34caa-218">SQL Server 2005-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34caa-218">SQL Server 2005 Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-219">bietet keine Unterstützung für die folgenden SQL Server 2005-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="34caa-219">does not support the following SQL Server 2005 features:</span></span>

- <span data-ttu-id="34caa-220">Gespeicherte Prozeduren für SQL CLR.</span><span class="sxs-lookup"><span data-stu-id="34caa-220">Stored procedures written for SQL CLR.</span></span>

- <span data-ttu-id="34caa-221">Benutzerdefinierter Typ.</span><span class="sxs-lookup"><span data-stu-id="34caa-221">User-defined type.</span></span>

- <span data-ttu-id="34caa-222">XML-Abfragefunktionen.</span><span class="sxs-lookup"><span data-stu-id="34caa-222">XML query features.</span></span>

## <a name="sql-server-2000-support"></a><span data-ttu-id="34caa-223">SQL Server 2000-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34caa-223">SQL Server 2000 Support</span></span>

<span data-ttu-id="34caa-224">Die folgenden 2000 SQL Server Einschränkungen (im Vergleich zu Microsoft SQL Server 2005) [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wirken sich auf die-Unterstützung aus.</span><span class="sxs-lookup"><span data-stu-id="34caa-224">The following SQL Server 2000 limitations (compared to Microsoft SQL Server 2005) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>

### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="34caa-225">Cross Apply-Operator und Outer Apply-Operator</span><span class="sxs-lookup"><span data-stu-id="34caa-225">Cross Apply and Outer Apply Operators</span></span>

<span data-ttu-id="34caa-226">Diese Operatoren sind in SQL Server 2000 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34caa-226">These operators are not available in SQL Server 2000.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="34caa-227">versucht eine Reihe von erneuten Schreibvorgängen, um sie durch entsprechende Joins zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="34caa-227">tries a series of rewrites to replace them with appropriate joins.</span></span>

<span data-ttu-id="34caa-228">`Cross Apply` und `Outer Apply` werden für Beziehungsnavigation erzeugt.</span><span class="sxs-lookup"><span data-stu-id="34caa-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="34caa-229">Der Satz von Abfragen, für den solche erneuten Schreibzugriffe möglich sind, ist nicht klar definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="34caa-230">Aus diesem Grund ist der minimale Satz von Abfragen, der für SQL Server 2000 unterstützt wird, der Satz, der keine Beziehungs Navigation umfasst.</span><span class="sxs-lookup"><span data-stu-id="34caa-230">For this reason, the minimal set of queries that is supported for SQL Server 2000 is the set that does not involve relationship navigation.</span></span>

### <a name="text--ntext"></a><span data-ttu-id="34caa-231">text / ntext</span><span class="sxs-lookup"><span data-stu-id="34caa-231">text / ntext</span></span>

<span data-ttu-id="34caa-232">-Daten `text` Typen  /  können`ntext`nicht in bestimmten Abfrage Vorgängen fürverwendetwerden,dievonMicrosoftSQLServer2005unterstütztwerden. /  `varchar(max)` `nvarchar(max)`</span><span class="sxs-lookup"><span data-stu-id="34caa-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by Microsoft SQL Server 2005.</span></span>

<span data-ttu-id="34caa-233">Für diese Einschränkung ist keine Lösung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34caa-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="34caa-234">Sie können insbesondere `Distinct()` nicht für Ergebnisse verwenden, die Member enthalten, die der `text`-Spalte oder der `ntext`-Spalte zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="34caa-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>

### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="34caa-235">Von verschachtelten Abfragen ausgelöstes Verhalten</span><span class="sxs-lookup"><span data-stu-id="34caa-235">Behavior Triggered by Nested Queries</span></span>

<span data-ttu-id="34caa-236">SQL Server 2000-Binder (über SP4) verfügt über einige idiosyncraasen, die durch geschachtelte Queries ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-236">SQL Server 2000 (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="34caa-237">Der Satz von SQL-Abfragen, der diese Eigenheiten auslöst, ist nicht klar definiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="34caa-238">Aus diesem Grund können Sie keine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen definieren, die SQL Server Ausnahmen verursachen können.</span><span class="sxs-lookup"><span data-stu-id="34caa-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>

### <a name="skip-and-take-operators"></a><span data-ttu-id="34caa-239">Skip-Operator und Take-Operator</span><span class="sxs-lookup"><span data-stu-id="34caa-239">Skip and Take Operators</span></span>

<span data-ttu-id="34caa-240"><xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> weisen bestimmte Einschränkungen auf, wenn sie für Abfragen in SQL Server 2000 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="34caa-241">Weitere Informationen finden Sie im Eintrag "überspringen und Entfernen von Ausnahmen in SQL Server 2000" in der [Problem](troubleshooting.md)Behandlung.</span><span class="sxs-lookup"><span data-stu-id="34caa-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="object-materialization"></a><span data-ttu-id="34caa-242">Objektmaterialisierung</span><span class="sxs-lookup"><span data-stu-id="34caa-242">Object Materialization</span></span>

<span data-ttu-id="34caa-243">Die Materialisierung erstellt CLR-Objekte aus Zeilen, die von einer oder mehreren SQL-Abfragen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>

- <span data-ttu-id="34caa-244">Die folgenden Aufrufe werden im Rahmen der Materialisierung *lokal ausgeführt* :</span><span class="sxs-lookup"><span data-stu-id="34caa-244">The following calls are *executed locally* as a part of materialization:</span></span>

  - <span data-ttu-id="34caa-245">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="34caa-245">Constructors</span></span>

  - <span data-ttu-id="34caa-246">`ToString`-Methoden in Projektionen</span><span class="sxs-lookup"><span data-stu-id="34caa-246">`ToString` methods in projections</span></span>

  - <span data-ttu-id="34caa-247">Typumwandlungen in Projektionen</span><span class="sxs-lookup"><span data-stu-id="34caa-247">Type casts in projections</span></span>

- <span data-ttu-id="34caa-248">Methoden, die der <xref:System.Linq.Enumerable.AsEnumerable%2A> -Methode folgen, werden *lokal ausgeführt*.</span><span class="sxs-lookup"><span data-stu-id="34caa-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="34caa-249">Diese Methode verursacht keine unmittelbare Ausführung.</span><span class="sxs-lookup"><span data-stu-id="34caa-249">This method does not cause immediate execution.</span></span>

- <span data-ttu-id="34caa-250">Sie können einen `struct` als Rückgabetyp eines Abfrageergebnisses oder als Member des Ergebnistyps verwenden.</span><span class="sxs-lookup"><span data-stu-id="34caa-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="34caa-251">Entitäten müssen Klassen sein.</span><span class="sxs-lookup"><span data-stu-id="34caa-251">Entities are required to be classes.</span></span> <span data-ttu-id="34caa-252">Anonyme Typen werden als Klasseninstanzen materialisiert. Benannte structs (Nicht-Entitäten) können jedoch in Projektionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34caa-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>

- <span data-ttu-id="34caa-253">Ein Member des Rückgabetyps eines Abfrageergebnisses kann vom Typ <xref:System.Linq.IQueryable%601> sein.</span><span class="sxs-lookup"><span data-stu-id="34caa-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="34caa-254">Er wird als lokale Auflistung materialisiert.</span><span class="sxs-lookup"><span data-stu-id="34caa-254">It is materialized as a local collection.</span></span>

- <span data-ttu-id="34caa-255">Die folgenden Methoden verursachen die *sofortige Materialisierung* der Sequenz, auf die die Methoden angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="34caa-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a><span data-ttu-id="34caa-256">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34caa-256">See also</span></span>

- [<span data-ttu-id="34caa-257">Verweis</span><span class="sxs-lookup"><span data-stu-id="34caa-257">Reference</span></span>](reference.md)
- [<span data-ttu-id="34caa-258">Zurückgeben oder Überspringen von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="34caa-258">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)
- [<span data-ttu-id="34caa-259">Verketten von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="34caa-259">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)
- [<span data-ttu-id="34caa-260">Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="34caa-260">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)
- [<span data-ttu-id="34caa-261">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="34caa-261">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)
- [<span data-ttu-id="34caa-262">Zurückgeben der Vereinigungsmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="34caa-262">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)
