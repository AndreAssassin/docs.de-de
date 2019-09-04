---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: b7393bef32b3e057eca51eb516cb72cd2de126c2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248964"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="d4082-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d4082-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="d4082-103">Behandelt ein Objekt eines bestimmten Basistyps als Objekt des angegebenen abgeleiteten Typs.</span><span class="sxs-lookup"><span data-stu-id="d4082-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4082-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4082-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4082-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d4082-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d4082-106">Jeder gültige Abfrageausdruck, der eine Entität zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d4082-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4082-107">Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.</span><span class="sxs-lookup"><span data-stu-id="d4082-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="d4082-108">Ein Entitätstyp.</span><span class="sxs-lookup"><span data-stu-id="d4082-108">An entity type.</span></span> <span data-ttu-id="d4082-109">Der Typ muss mit einem Namespace qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d4082-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4082-110">Beim Typ des angegebenen Ausdrucks muss es sich um einen Untertyp des angegebenen Datentyps oder umgekehrt handeln.</span><span class="sxs-lookup"><span data-stu-id="d4082-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4082-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4082-111">Return Value</span></span>  
 <span data-ttu-id="d4082-112">Ein Wert des angegebenen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="d4082-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4082-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4082-113">Remarks</span></span>  
 <span data-ttu-id="d4082-114">TREAT wird zum Umwandeln zwischen verknüpften Klassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4082-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="d4082-115">Wenn z. B. `Employee` von `Person` abgeleitet ist und "p" vom Typ `Person`ist, wandelt `TREAT(p AS NamespaceName.Employee)` eine generische `Person` -Instanz in `Employee`um. Das bedeutet, dass "p" als `Employee`behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4082-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="d4082-116">TREAT wird in Vererbungsszenarios verwendet, in denen eine Abfrage wie die folgende möglich ist:</span><span class="sxs-lookup"><span data-stu-id="d4082-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="d4082-117">In dieser Abfrage werden `Person` -Entitäten in den `Employee` -Typ umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="d4082-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="d4082-118">Wenn der Wert von "p" nicht tatsächlich vom Typ `Employee`ist, gibt der Ausdruck den Wert `null`zurück.</span><span class="sxs-lookup"><span data-stu-id="d4082-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4082-119">Der angegebene Ausdruck `Employee` muss ein Untertyp des angegebenen Datentyps `Person`sein, oder der Datentyp muss ein Untertyp des Ausdrucks sein.</span><span class="sxs-lookup"><span data-stu-id="d4082-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="d4082-120">Andernfalls führt der Ausdruck zu einem Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="d4082-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="d4082-121">In der folgenden Tabelle wird das Verhalten von TREAT für einige typische und weniger typische Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4082-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="d4082-122">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="d4082-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d4082-123">Muster</span><span class="sxs-lookup"><span data-stu-id="d4082-123">Pattern</span></span>|<span data-ttu-id="d4082-124">Verhalten</span><span class="sxs-lookup"><span data-stu-id="d4082-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="d4082-125">Gibt `DbNull`zurück.</span><span class="sxs-lookup"><span data-stu-id="d4082-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="d4082-126">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d4082-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="d4082-127">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d4082-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="d4082-128">Gibt einen `EntityType` oder `null`zurück.</span><span class="sxs-lookup"><span data-stu-id="d4082-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="d4082-129">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d4082-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="d4082-130">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d4082-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4082-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4082-131">Example</span></span>  
 <span data-ttu-id="d4082-132">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der TREAT-Operator verwendet, um ein Objekt des Typs "Kurs" in eine Auflistung von Objekten des Typs "OnsiteCourse" umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="d4082-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="d4082-133">Die Abfrage basiert auf dem [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d4082-133">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="d4082-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4082-134">See also</span></span>

- [<span data-ttu-id="d4082-135">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d4082-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d4082-136">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="d4082-136">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
