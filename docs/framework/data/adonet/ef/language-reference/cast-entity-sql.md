---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: 51de041a4b06d5da31071ea2b3cb31c86feff137
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294444"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="6b340-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6b340-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="6b340-103">Konvertiert einen Ausdruck von einem Datentyp in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="6b340-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b340-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b340-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b340-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6b340-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6b340-106">Ein gültiger Ausdruck, der zu `data_type`konvertierbar ist.</span><span class="sxs-lookup"><span data-stu-id="6b340-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="6b340-107">Der vom Zielsystem bereitgestellte Datentyp.</span><span class="sxs-lookup"><span data-stu-id="6b340-107">The target system-supplied data type.</span></span> <span data-ttu-id="6b340-108">Dabei muss es sich um einen primitiven (skalaren) Typ handeln.</span><span class="sxs-lookup"><span data-stu-id="6b340-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="6b340-109">Der verwendete `data_type` hängt von der Abfrageumgebung ab.</span><span class="sxs-lookup"><span data-stu-id="6b340-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="6b340-110">Wird eine Abfrage mit dem <xref:System.Data.EntityClient.EntityCommand>ausgeführt, ist der Datentyp ein im konzeptionellen Modell definierter Typ.</span><span class="sxs-lookup"><span data-stu-id="6b340-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="6b340-111">Weitere Informationen finden Sie unter [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="6b340-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="6b340-112">Wenn eine Abfrage mit <xref:System.Data.Objects.ObjectQuery%601>ausgeführt wird, ist der Datentyp ein CLR-Typ.</span><span class="sxs-lookup"><span data-stu-id="6b340-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b340-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b340-113">Return Value</span></span>  
 <span data-ttu-id="6b340-114">Gibt denselben Wert zurück wie `data_type`.</span><span class="sxs-lookup"><span data-stu-id="6b340-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b340-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b340-115">Remarks</span></span>  
 <span data-ttu-id="6b340-116">Der CAST-Ausdruck verfügt über eine ähnliche Semantik wie der CONVERT-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b340-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="6b340-117">Der CAST-Ausdruck wird zum Konvertieren eines Werts von einem Typ in einen Wert von einem anderen Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b340-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="6b340-118">Wenn "e" vom Typ "S" ist und "S" zu "T" konvertierbar ist, ist der obige Ausdruck ein gültiger Umwandlungsausdruck.</span><span class="sxs-lookup"><span data-stu-id="6b340-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="6b340-119">"T" muss dabei ein primitiver (skalarer) Typ sein.</span><span class="sxs-lookup"><span data-stu-id="6b340-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="6b340-120">Beim Umwandeln in `Edm.Decimal`können Werte für die Facets der Genauigkeit und der Dezimalstellenanzahl bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b340-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="6b340-121">Werden keine expliziten Angaben gemacht, sind die Standardwerte für Genauigkeit und Dezimalstellenanzahl 18 bzw. 0.</span><span class="sxs-lookup"><span data-stu-id="6b340-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="6b340-122">Insbesondere werden folgende Überladungen von `Decimal`unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6b340-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="6b340-123">Die Verwendung eines Umwandlungsausdrucks wird als explizite Konvertierung aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="6b340-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="6b340-124">Explizite Konvertierungen können Daten abschneiden oder zu Genauigkeitsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="6b340-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b340-125">CAST wird nur für primitive Typen und Enumerationsmembertypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b340-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b340-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b340-126">Example</span></span>  
 <span data-ttu-id="6b340-127">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der CAST-Operator zum Umwandeln des Datentyps eines Ausdrucks in einen anderen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b340-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="6b340-128">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="6b340-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6b340-129">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="6b340-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6b340-130">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6b340-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="6b340-131">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="6b340-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="6b340-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b340-132">See also</span></span>

- [<span data-ttu-id="6b340-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6b340-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
