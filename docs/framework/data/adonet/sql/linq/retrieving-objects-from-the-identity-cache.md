---
title: Abrufen von Objekten aus dem Identitätscache
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: a8e4fc9b83e11aef4347ab4765f6a2e75c526387
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910752"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="d6a57-102">Abrufen von Objekten aus dem Identitätscache</span><span class="sxs-lookup"><span data-stu-id="d6a57-102">Retrieving Objects from the Identity Cache</span></span>
<span data-ttu-id="d6a57-103">In diesem Thema werden die Typen von LINQ to SQL-Abfragen beschrieben, die Objekte aus dem Identitäts-Cache abrufen, der vom <xref:System.Data.Linq.DataContext> verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="d6a57-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="d6a57-104">In LINQ to SQL besteht eine der Methoden zur <xref:System.Data.Linq.DataContext>-Objektverwaltung darin, Objektidentitäten in einem Identitäts-Cache zu protokollieren, während Abfragen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6a57-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="d6a57-105">In einigen Fällen versucht LINQ to SQL, vor dem Ausführen einer Datenbankabfrage ein Objekt aus dem Identitäts-Cache abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d6a57-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="d6a57-106">Damit eine LINQ to SQL-Abfrage ein Objekt aus dem Identitäts-Cache zurückgibt, muss die Abfrage im Regelfall auf dem Primärschlüssel eines Objekts basieren und ein einzelnes Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d6a57-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="d6a57-107">Die Abfrage muss eine der im Folgenden gezeigten allgemeinen Formen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d6a57-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6a57-108">Vorkompilierte Abfrage geben keine Objekte aus dem Identitäts-Cache zurück.</span><span class="sxs-lookup"><span data-stu-id="d6a57-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="d6a57-109">Weitere Informationen über vorkompilierte Abfragen finden Sie unter <xref:System.Data.Linq.CompiledQuery> und [Vorgehensweise: Store und Wiederverwenden von Abfragen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d6a57-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="d6a57-110">Eine Abfrage muss eine der folgenden allgemeinen Formen aufweisen, um ein Objekt aus dem Identitäts-Cache abzurufen:</span><span class="sxs-lookup"><span data-stu-id="d6a57-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
- <span data-ttu-id="d6a57-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="d6a57-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
- <span data-ttu-id="d6a57-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="d6a57-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="d6a57-113">In diesen allgemeinen Formen werden `Function1`, `Function2` und `predicate` wie folgt definiert.</span><span class="sxs-lookup"><span data-stu-id="d6a57-113">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="d6a57-114">`Function1` kann eine der folgenden Formen haben:</span><span class="sxs-lookup"><span data-stu-id="d6a57-114">`Function1` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="d6a57-115">`Function2` kann eine der folgenden Formen haben:</span><span class="sxs-lookup"><span data-stu-id="d6a57-115">`Function2` can be any of the following:</span></span>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="d6a57-116">`predicate` muss ein Ausdruck sein, in dem die Primärschlüsseleigenschaft des Objekts auf einen konstanten Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d6a57-116">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="d6a57-117">Wenn der Primärschlüssel eines Objekts von mehreren Eigenschaften definiert wird, muss jede dieser Eigenschaften auf einen konstanten Wert festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="d6a57-117">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="d6a57-118">Hier einige Beispiele der Form, die `predicate` aufweisen muss:</span><span class="sxs-lookup"><span data-stu-id="d6a57-118">The following are examples of the form `predicate` must take:</span></span>  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="d6a57-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6a57-119">Example</span></span>  
 <span data-ttu-id="d6a57-120">Der folgende Code stellt Beispiele für die Typen von LINQ to SQL-Abfragen dar, die ein Objekt aus dem Identitäts-Cache abrufen.</span><span class="sxs-lookup"><span data-stu-id="d6a57-120">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d6a57-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6a57-121">See also</span></span>

- [<span data-ttu-id="d6a57-122">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="d6a57-122">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="d6a57-123">Objektidentität</span><span class="sxs-lookup"><span data-stu-id="d6a57-123">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
- [<span data-ttu-id="d6a57-124">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="d6a57-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="d6a57-125">Objektidentität</span><span class="sxs-lookup"><span data-stu-id="d6a57-125">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
