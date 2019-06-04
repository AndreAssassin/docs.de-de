---
title: Aggregieren kanonischer Funktionen
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 2738d649190b088c34272de5b3e8732d87811a59
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489510"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="43bb5-102">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="43bb5-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="43bb5-103">Aggregate sind Ausdrücke, die eine Folge von Eingabewerten beispielsweise auf einen einzigen Wert reduzieren.</span><span class="sxs-lookup"><span data-stu-id="43bb5-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="43bb5-104">Aggregate werden normalerweise zusammen mit der GROUP BY-Klausel des SELECT-Ausdrucks verwendet, und für ihre Verwendung gelten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="43bb5-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="43bb5-105">Aggregieren kanonischer Funktionen von Entity SQL</span><span class="sxs-lookup"><span data-stu-id="43bb5-105">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="43bb5-106">Im folgenden werden die kanonischen Entity SQL-Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="43bb5-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="43bb5-107">Avg (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-107">Avg(expression)</span></span>

<span data-ttu-id="43bb5-108">Gibt den Durchschnitt der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="43bb5-109">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-109">**Arguments**</span></span>

<span data-ttu-id="43bb5-110">Ein `Int32`, `Int64`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="43bb5-111">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-111">**Return Value**</span></span>

<span data-ttu-id="43bb5-112">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-113">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="43bb5-114">BigCount (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-114">BigCount(expression)</span></span>

<span data-ttu-id="43bb5-115">Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="43bb5-116">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-116">**Arguments**</span></span>

<span data-ttu-id="43bb5-117">Beliebiger Typ.</span><span class="sxs-lookup"><span data-stu-id="43bb5-117">Any type.</span></span>

<span data-ttu-id="43bb5-118">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-118">**Return Value**</span></span>

<span data-ttu-id="43bb5-119">Eine `Int64`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-119">An `Int64`.</span></span>

<span data-ttu-id="43bb5-120">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="43bb5-121">Count (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-121">Count(expression)</span></span>

<span data-ttu-id="43bb5-122">Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="43bb5-123">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-123">**Arguments**</span></span>

<span data-ttu-id="43bb5-124">Beliebiger Typ.</span><span class="sxs-lookup"><span data-stu-id="43bb5-124">Any type.</span></span>

<span data-ttu-id="43bb5-125">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-125">**Return Value**</span></span>

<span data-ttu-id="43bb5-126">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-126">An `Int32`.</span></span>

<span data-ttu-id="43bb5-127">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="43bb5-128">Max (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-128">Max(expression)</span></span>

<span data-ttu-id="43bb5-129">Gibt den Höchstwert der von null verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="43bb5-130">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-130">**Arguments**</span></span>

<span data-ttu-id="43bb5-131">`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .</span><span class="sxs-lookup"><span data-stu-id="43bb5-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="43bb5-132">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-132">**Return Value**</span></span>

<span data-ttu-id="43bb5-133">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-134">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="43bb5-135">Min (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-135">Min(expression)</span></span>

<span data-ttu-id="43bb5-136">Gibt den geringsten Wert der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="43bb5-137">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-137">**Arguments**</span></span>

<span data-ttu-id="43bb5-138">`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .</span><span class="sxs-lookup"><span data-stu-id="43bb5-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="43bb5-139">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-139">**Return Value**</span></span>

<span data-ttu-id="43bb5-140">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-141">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="43bb5-142">StDev (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-142">StDev(expression)</span></span>

<span data-ttu-id="43bb5-143">Gibt die Standardabweichung der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="43bb5-144">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-144">**Arguments**</span></span>

<span data-ttu-id="43bb5-145">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="43bb5-146">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-146">**Return Value**</span></span>

<span data-ttu-id="43bb5-147">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-147">A `Double`.</span></span> <span data-ttu-id="43bb5-148">`Null`, wenn alle Eingabewerte `null`-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="43bb5-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-149">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="43bb5-150">StDevP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-150">StDevP(expression)</span></span>

<span data-ttu-id="43bb5-151">Gibt die Standardabweichung zum Ausfüllen aller Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="43bb5-152">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-152">**Arguments**</span></span>

<span data-ttu-id="43bb5-153">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="43bb5-154">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-154">**Return Value**</span></span>

<span data-ttu-id="43bb5-155">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-156">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="43bb5-157">Sum (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-157">Sum(expression)</span></span>

<span data-ttu-id="43bb5-158">Gibt die Summe der von null verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="43bb5-159">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-159">**Arguments**</span></span>

<span data-ttu-id="43bb5-160">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="43bb5-161">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-161">**Return Value**</span></span>

<span data-ttu-id="43bb5-162">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-163">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="43bb5-164">Var (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-164">Var(expression)</span></span>

<span data-ttu-id="43bb5-165">Gibt die Varianz aller Werte zurück, die keine Null-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="43bb5-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="43bb5-166">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-166">**Arguments**</span></span>

<span data-ttu-id="43bb5-167">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="43bb5-168">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-168">**Return Value**</span></span>

<span data-ttu-id="43bb5-169">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-170">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="43bb5-171">VarP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="43bb5-171">VarP(expression)</span></span>

<span data-ttu-id="43bb5-172">Gibt die Varianz für die Auffüllung aller Werte zurück, die keine Null-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="43bb5-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="43bb5-173">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="43bb5-173">**Arguments**</span></span>

<span data-ttu-id="43bb5-174">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43bb5-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="43bb5-175">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="43bb5-175">**Return Value**</span></span>

<span data-ttu-id="43bb5-176">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="43bb5-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="43bb5-177">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="43bb5-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="43bb5-178">Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43bb5-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="43bb5-179">Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="43bb5-179">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="43bb5-180">Auflistungsbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="43bb5-180">Collection-based aggregates</span></span>

<span data-ttu-id="43bb5-181">Auflistungsbasierte Aggregate (Auflistungsfunktionen) verarbeiten Auflistungen und geben einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="43bb5-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="43bb5-182">Zum Beispiel wenn ORDERS ist eine Auflistung aller Bestellungen, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:</span><span class="sxs-lookup"><span data-stu-id="43bb5-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="43bb5-183">Ausdrücke in auflistungsbasierten Aggregaten werden innerhalb des aktuellen umgebenden Namensauflösungsbereichs ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="43bb5-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="43bb5-184">Gruppenbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="43bb5-184">Group-based aggregates</span></span>

<span data-ttu-id="43bb5-185">Gruppenbasierte Aggregate werden für eine Gruppe berechnet, die mit einer GROUP BY-Klausel definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="43bb5-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="43bb5-186">Für jede Gruppe im Ergebnis wird ein separates Aggregat berechnet, indem die Elemente in jeder Gruppe als Eingabe zur Aggregatberechnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43bb5-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="43bb5-187">Wenn eine GROUP BY-Klausel in einem SELECT-Ausdruck verwendet wird, können sich in der Projektion oder ORDER BY-Klausel nur die Namen von Gruppierungsausdrücken, Aggregate oder konstante Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="43bb5-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="43bb5-188">Im folgenden Beispiel wird die durchschnittlich bestellte Anzahl für jedes Produkt berechnet:</span><span class="sxs-lookup"><span data-stu-id="43bb5-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="43bb5-189">Es ist möglich, eine Gruppenbasierte Aggregate ohne explizite Group by-Klausel im SELECT-Ausdruck haben.</span><span class="sxs-lookup"><span data-stu-id="43bb5-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="43bb5-190">In diesem Fall werden alle Elemente als eine einzelne Gruppe behandelt.</span><span class="sxs-lookup"><span data-stu-id="43bb5-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="43bb5-191">Dies entspricht der Angabe einer Gruppe auf Grundlage einer Konstante.</span><span class="sxs-lookup"><span data-stu-id="43bb5-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="43bb5-192">Betrachten Sie beispielsweise folgenden Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="43bb5-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="43bb5-193">Dieser Ausdruck ist äquivalent zu Folgendem:</span><span class="sxs-lookup"><span data-stu-id="43bb5-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="43bb5-194">Ausdrücke in gruppenbasierten Aggregaten werden innerhalb des Namensauflösungsbereichs ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.</span><span class="sxs-lookup"><span data-stu-id="43bb5-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="43bb5-195">Wie in Transact-SQL, Gruppenbasierte Aggregate können auch angeben, alles oder DISTINCT-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="43bb5-195">As in Transact-SQL, group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="43bb5-196">Wenn der DISTINCT-Modifizierer angegeben ist, werden Duplikate vor der Berechnung des Aggregats aus der Aggregateingabeauflistung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="43bb5-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="43bb5-197">Wenn der ALL-Modifizierer oder kein Modifizierer angegeben wird, werden Duplikate nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="43bb5-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="43bb5-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43bb5-198">See also</span></span>

- [<span data-ttu-id="43bb5-199">Canonical Functions (Kanonische Funktionen)</span><span class="sxs-lookup"><span data-stu-id="43bb5-199">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
