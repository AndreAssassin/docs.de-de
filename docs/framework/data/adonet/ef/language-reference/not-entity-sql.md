---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 51d3bdbc4adb0b5fd6275629219698dd9b42fa86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760375"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="6b099-103">!</span><span class="sxs-lookup"><span data-stu-id="6b099-103">!</span></span> <span data-ttu-id="6b099-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6b099-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="6b099-105">Negiert einen `Boolean` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6b099-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b099-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b099-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b099-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="6b099-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="6b099-108">Jeder gültige Ausdruck, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6b099-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b099-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b099-109">Remarks</span></span>  
 <span data-ttu-id="6b099-110">Das Ausrufezeichen (!) hat dieselbe Bedeutung wie der NOT-Operator.</span><span class="sxs-lookup"><span data-stu-id="6b099-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b099-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b099-111">Example</span></span>  
 <span data-ttu-id="6b099-112">Die folgende Entity SQL-Abfrage verwendet den NOT-Operator, um einen `Boolean` -Ausdruck zu negieren.</span><span class="sxs-lookup"><span data-stu-id="6b099-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="6b099-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="6b099-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6b099-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="6b099-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6b099-115">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6b099-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6b099-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="6b099-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="6b099-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b099-117">See also</span></span>

- [<span data-ttu-id="6b099-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6b099-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
