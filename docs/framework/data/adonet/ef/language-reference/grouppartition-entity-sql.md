---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 9f0f917380e6422da753282216529580f87f1a1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774724"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="2783c-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2783c-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="2783c-103">Gibt eine Auflistung von Argumentwerten zurück, die für die aktuelle Gruppenpartition projiziert werden, auf die sich das Aggregat bezieht.</span><span class="sxs-lookup"><span data-stu-id="2783c-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="2783c-104">Das `GroupPartition` -Aggregat ist ein gruppenbasiertes Aggregat und weist kein auflistungsbasiertes Formular auf.</span><span class="sxs-lookup"><span data-stu-id="2783c-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2783c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2783c-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="2783c-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="2783c-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2783c-107">Beliebiger [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2783c-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2783c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2783c-108">Remarks</span></span>  
 <span data-ttu-id="2783c-109">Die folgende Abfrage erzeugt eine Liste von Produkten und eine Auflistung von Reihenfolgenzeilenmengen für jedes Produkt:</span><span class="sxs-lookup"><span data-stu-id="2783c-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="2783c-110">Die folgenden zwei Abfragen stimmen semantisch überein:</span><span class="sxs-lookup"><span data-stu-id="2783c-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="2783c-111">Der `GROUPPARTITION` -Operator kann in Verbindung mit benutzerdefinierten Aggregatfunktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2783c-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="2783c-112">`GROUPPARTITION` ist ein besonderer Aggregatoperator, der einen Verweis auf den gruppierten Eingabesatz beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="2783c-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="2783c-113">Dieser Verweis kann an einer beliebigen Stelle in der Abfrage verwendet werden, an der sich GROUP BY innerhalb des Bereichs befindet.</span><span class="sxs-lookup"><span data-stu-id="2783c-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="2783c-114">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="2783c-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="2783c-115">Bei einem regulären GROUP BY werden die Ergebnisse des Gruppiervorgangs ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="2783c-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="2783c-116">Sie können die Ergebnisse nur in einer Aggregatfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="2783c-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="2783c-117">Zum Anzeigen der Ergebnisse des Gruppiervorgangs müssen die Ergebnisse des Gruppiervorgangs und des Eingabesets mithilfe einer Unterabfrage korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="2783c-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="2783c-118">Die folgenden beiden Abfragen sind gleichwertig:</span><span class="sxs-lookup"><span data-stu-id="2783c-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="2783c-119">Wie im Beispiel gezeigt, wird durch den GROUPPARTITION-Aggregatoperator das Abrufen einen Verweises auf den Eingabesatz nach dem Gruppiervorgang vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="2783c-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="2783c-120">Der GROUPPARTITION-Operator kann bei Verwendung des [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Parameters einen beliebigen `expression` -Ausdruck im Operator angeben.</span><span class="sxs-lookup"><span data-stu-id="2783c-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="2783c-121">Zum Beispiel sind die folgenden Eingabeausdrücke für die Gruppenpartition gültig:</span><span class="sxs-lookup"><span data-stu-id="2783c-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="2783c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2783c-122">Example</span></span>  
 <span data-ttu-id="2783c-123">Im folgenden Beispiel wird gezeigt, wie die GROUPPARTITION-Klausel mit der GROUP BY-Klausel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2783c-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="2783c-124">Die GROUP BY-Klausel gruppiert `SalesOrderHeader` -Entitäten nach `Contact`.</span><span class="sxs-lookup"><span data-stu-id="2783c-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="2783c-125">Die GROUPPARTITION-Klausel projiziert dann für jede Gruppe die `TotalDue` -Eigenschaft, woraus sich eine Auflistung von Dezimalwerten ergibt.</span><span class="sxs-lookup"><span data-stu-id="2783c-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
