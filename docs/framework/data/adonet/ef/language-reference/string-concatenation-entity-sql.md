---
title: + (Verketten) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 5f2c031218a9e533889c696bc592e73a27b51d06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329764"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="46592-102">+ (Zeichenfolgenverkettung) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="46592-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="46592-103">Verkettet zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="46592-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46592-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46592-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="46592-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="46592-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="46592-106">Jeder gültige Ausdruck des Datentyps EDM.String.</span><span class="sxs-lookup"><span data-stu-id="46592-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="46592-107">Beide Ausdrücke müssen denselben Datentyp aufweisen, oder ein Ausdruck muss implizit in den Datentyp des anderen Ausdrucks konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="46592-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="46592-108">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="46592-108">Result Types</span></span>  
 <span data-ttu-id="46592-109">Der Datentyp, der sich aus der impliziten Datentyphöherstufung der zwei Argumente ergibt.</span><span class="sxs-lookup"><span data-stu-id="46592-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="46592-110">Weitere Informationen zur impliziten datentyphöherstufung finden Sie unter [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="46592-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46592-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46592-111">Example</span></span>  
 <span data-ttu-id="46592-112">Die folgende Entity SQL-Abfrage verwendet den Operator "+", um zwei Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="46592-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="46592-113">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="46592-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="46592-114">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="46592-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="46592-115">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="46592-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="46592-116">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="46592-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="46592-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46592-117">See also</span></span>

- [<span data-ttu-id="46592-118">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="46592-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="46592-119">Konzeptionelle Modelltypen (CSDL)</span><span class="sxs-lookup"><span data-stu-id="46592-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
