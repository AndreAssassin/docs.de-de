---
title: '> (Größer als) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: e1d13fa863eb79982d239f4e2dc298f7fcd1346f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328555"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="565e7-102">> (Größer als) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="565e7-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="565e7-103">Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="565e7-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="565e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="565e7-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="565e7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="565e7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="565e7-106">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="565e7-106">Any valid expression.</span></span> <span data-ttu-id="565e7-107">Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.</span><span class="sxs-lookup"><span data-stu-id="565e7-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="565e7-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="565e7-108">Result Types</span></span>  
 `true` <span data-ttu-id="565e7-109">Wenn der linke Ausdruck größer als der rechte Ausdruck ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="565e7-109">if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="565e7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="565e7-110">Example</span></span>  
 <span data-ttu-id="565e7-111">In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator > verwendet, um zu ermitteln, ob der linke Ausdruck größer als der rechte Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="565e7-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="565e7-112">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="565e7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="565e7-113">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="565e7-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="565e7-114">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="565e7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="565e7-115">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="565e7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="565e7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="565e7-116">See also</span></span>

- [<span data-ttu-id="565e7-117">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="565e7-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
