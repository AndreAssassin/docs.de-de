---
title: '>= (Größer als oder gleich) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: fb97786687616ff92f0e4402c86aef02de2e70c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250873"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="7b8dd-102">> = (größer als oder gleich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7b8dd-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="7b8dd-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b8dd-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7b8dd-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7b8dd-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7b8dd-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-106">Any valid expression.</span></span> <span data-ttu-id="7b8dd-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7b8dd-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="7b8dd-108">Result Types</span></span>  
 <span data-ttu-id="7b8dd-109">`true` , wenn der linke Ausdruck größer oder gleich dem rechten Ausdruck ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b8dd-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b8dd-110">Example</span></span>  
 <span data-ttu-id="7b8dd-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator >= verwendet, um zu ermitteln, ob der linke Ausdruck größer oder gleich dem rechten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="7b8dd-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7b8dd-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7b8dd-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7b8dd-114">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7b8dd-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="7b8dd-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="7b8dd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b8dd-116">See also</span></span>

- [<span data-ttu-id="7b8dd-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="7b8dd-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
