---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: f1dd5ba92c7b1eaf7117c9732a78e04e5d5a317a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319458"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="cda2c-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cda2c-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="cda2c-103">Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="cda2c-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cda2c-104">Syntax</span></span>  
  
```sql  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cda2c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cda2c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cda2c-106">Jeder gültige Abfrageausdruck, der eine Auflistung von Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cda2c-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="cda2c-107">Der Typ, dessen Übereinstimmung mit jedem von `expression` zurückgegebenen Objekt getestet wird.</span><span class="sxs-lookup"><span data-stu-id="cda2c-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="cda2c-108">Der Typ muss mit einem Namespace qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="cda2c-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cda2c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cda2c-109">Return Value</span></span>  
 <span data-ttu-id="cda2c-110">Eine Auflistung von Objekten vom Typ `test_type`, von einem Basistyp oder von einem von `test_type`abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="cda2c-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="cda2c-111">Wenn ONLY angegeben wird, werden nur Instanzen des `test_type` oder eine leere Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cda2c-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cda2c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cda2c-112">Remarks</span></span>  
 <span data-ttu-id="cda2c-113">Ein `OFTYPE` -Ausdruck stellt einen Typausdruck dar, der angegeben wird, um einen Typtest für jedes Element einer Auflistung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cda2c-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="cda2c-114">Der `OFTYPE` -Ausdruck liefert eine neue Auflistung des angegebenen Typs, die nur die zu diesem Typ oder einem seiner Untertypen äquivalenten Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="cda2c-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="cda2c-115">Ein `OFTYPE` -Ausdruck ist eine Abkürzung des folgenden Abfrageausdrucks:</span><span class="sxs-lookup"><span data-stu-id="cda2c-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```sql  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="cda2c-116">Wenn beispielsweise "Manager" ein Untertyp von "Employee" (Mitarbeiter) ist, liefert der folgende Ausdruck nur die Manager aus einer Auflistung der Mitarbeiter:</span><span class="sxs-lookup"><span data-stu-id="cda2c-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```sql  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="cda2c-117">Mithilfe des Typfilters kann eine Auflistung auch umgewandelt werden:</span><span class="sxs-lookup"><span data-stu-id="cda2c-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```sql
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="cda2c-118">Da alle Direktoren Manager sind, enthält die resultierende Auflistung alle Direktoren, auch wenn die Auflistung nun als eine Auflistung von Managern typisiert ist.</span><span class="sxs-lookup"><span data-stu-id="cda2c-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="cda2c-119">In der folgenden Tabelle wird das Verhalten des `OFTYPE` -Operators für verschiedene Muster dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cda2c-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="cda2c-120">Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="cda2c-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="cda2c-121">Muster</span><span class="sxs-lookup"><span data-stu-id="cda2c-121">Pattern</span></span>|<span data-ttu-id="cda2c-122">Verhalten</span><span class="sxs-lookup"><span data-stu-id="cda2c-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="cda2c-123">OFTYPE (Collection(EntityType), (EntityType)</span><span class="sxs-lookup"><span data-stu-id="cda2c-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="cda2c-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="cda2c-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="cda2c-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="cda2c-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="cda2c-126">Löst aus</span><span class="sxs-lookup"><span data-stu-id="cda2c-126">Throws</span></span>|  
|<span data-ttu-id="cda2c-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="cda2c-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="cda2c-128">Löst aus</span><span class="sxs-lookup"><span data-stu-id="cda2c-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cda2c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cda2c-129">Example</span></span>  
 <span data-ttu-id="cda2c-130">Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage verwendet den OFTYPE-Operator, um eine Auflistung der OnsiteCourse-Objekte von einer Auflistung von Kursobjekten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="cda2c-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="cda2c-131">Die Abfrage basiert auf dem [Modell "School"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cda2c-131">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OFTYPE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="cda2c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda2c-132">See also</span></span>

- [<span data-ttu-id="cda2c-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="cda2c-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
