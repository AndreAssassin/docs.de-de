---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 10c5ecb2b44c85dccd758cc1cf63a152da045cc1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251084"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="3bea5-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3bea5-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="3bea5-103">Dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="3bea5-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bea5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bea5-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="3bea5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3bea5-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3bea5-106">Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3bea5-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bea5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3bea5-107">Return Value</span></span>  
 <span data-ttu-id="3bea5-108">Der Wert der Entität, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3bea5-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bea5-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bea5-109">Remarks</span></span>  
 <span data-ttu-id="3bea5-110">Der DEREF-Operator dereferenziert einen Verweiswert und erstellt das Ergebnis dieser Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="3bea5-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="3bea5-111">Wenn `r` z. b. ein Verweis vom Typ Ref\<T > ist `Deref(r)` , ist ein Ausdruck vom `T` Typ, der die Entität `r`ergibt, auf die von verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3bea5-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="3bea5-112">Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht existiert, hat das Ergebnis des DEREF-Operators den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="3bea5-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bea5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bea5-113">Example</span></span>  
 <span data-ttu-id="3bea5-114">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der DEREF-Operator verwendet, um einen Verweiswert zu dereferenzieren und das Ergebnis dieser Dereferenzierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3bea5-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="3bea5-115">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="3bea5-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3bea5-116">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3bea5-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3bea5-117">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die PrimitiveType-Ergebnisse](../how-to-execute-a-query-that-returns-primitivetype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3bea5-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3bea5-118">Übergeben Sie die folgende Abfrage als Argument an die ExecutePrimitiveTypeQuery-Methode:</span><span class="sxs-lookup"><span data-stu-id="3bea5-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="3bea5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bea5-119">See also</span></span>

- [<span data-ttu-id="3bea5-120">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3bea5-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="3bea5-121">REF</span><span class="sxs-lookup"><span data-stu-id="3bea5-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="3bea5-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="3bea5-122">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="3bea5-123">KEY</span><span class="sxs-lookup"><span data-stu-id="3bea5-123">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="3bea5-124">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="3bea5-124">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
