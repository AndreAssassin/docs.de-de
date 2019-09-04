---
title: Form der Befehlsstrukturen
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: a3568f3deeaeeb31b69b41ac7c767001b792a8eb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248223"
---
# <a name="the-shape-of-the-command-trees"></a><span data-ttu-id="4b254-102">Form der Befehlsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4b254-102">The Shape of the Command Trees</span></span>

<span data-ttu-id="4b254-103">Das SQL-Generierungsmodul generiert anhand eines angegebenen Eingabeabfragebefehlsstruktur-Ausdrucks eine Back-End-spezifische SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="4b254-103">The SQL generation module is responsible for generating a backend specific SQL query based on a given input query command tree expression.</span></span> <span data-ttu-id="4b254-104">In diesem Abschnitt werden die Merkmale, die Eigenschaften und die Struktur der Abfragebefehlsstrukturen erläutert.</span><span class="sxs-lookup"><span data-stu-id="4b254-104">This section discusses the characteristics, properties, and structure of the query command trees.</span></span>

## <a name="query-command-trees-overview"></a><span data-ttu-id="4b254-105">Übersicht über die Abfragebefehlsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4b254-105">Query Command Trees Overview</span></span>

<span data-ttu-id="4b254-106">Bei einer Abfragebefehlsstruktur handelt es sich um die Objektmodelldarstellung einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="4b254-106">A query command tree is an object model representation of a query.</span></span> <span data-ttu-id="4b254-107">Abfragebefehlsstrukturen dienen zwei Zwecken:</span><span class="sxs-lookup"><span data-stu-id="4b254-107">Query command trees serve two purposes:</span></span>

- <span data-ttu-id="4b254-108">Dem Ausdrücken einer Eingabeabfrage für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b254-108">To express an input query that is specified against the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>

- <span data-ttu-id="4b254-109">Dem Ausdrücken eine Ausgabeabfrage, die einem Anbieter übergeben wird und eine Back-End-Abfrage beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4b254-109">To express an output query that is given to a provider and describes a query against the backend.</span></span>

<span data-ttu-id="4b254-110">Abfragebefehlsstrukturen unterstützen eine umfangreichere Semantik als SQL:1999-kompatible Abfragen. Dies umfasst die Unterstützung von geschachtelten Auflistungen und Typvorgängen, z. B. bei der Prüfung, ob es sich bei einer Entität um einen bestimmten Typ handelt, oder beim Filtern von Sätzen anhand eines Typs.</span><span class="sxs-lookup"><span data-stu-id="4b254-110">Query command trees support richer semantics than SQL:1999 compliant queries, including support for working with nested collections and type operations, like checking whether an entity is of a particular type, or filtering sets based on a type.</span></span>

<span data-ttu-id="4b254-111">Die „DBQueryCommandTree.Query“-Eigenschaft ist der Stamm der Ausdrucksbaumstruktur, die die Abfragelogik beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4b254-111">The DBQueryCommandTree.Query property is the root of the expression tree that describes the query logic.</span></span> <span data-ttu-id="4b254-112">Die "DBQueryCommandTree.Parameters"-Eigenschaft enthält eine Liste der in der Abfrage verwendeten Parameter.</span><span class="sxs-lookup"><span data-stu-id="4b254-112">The DBQueryCommandTree.Parameters property contains a list of parameters that are used in the query.</span></span> <span data-ttu-id="4b254-113">Die Ausdrucksstruktur besteht aus "DbExpression"-Objekten.</span><span class="sxs-lookup"><span data-stu-id="4b254-113">The expression tree is composed of DbExpression objects.</span></span>

<span data-ttu-id="4b254-114">Ein "DbExpression"-Objekt stellt eine Berechnung dar.</span><span class="sxs-lookup"><span data-stu-id="4b254-114">A DbExpression object represents some computation.</span></span> <span data-ttu-id="4b254-115">Zum Verfassen von Abfrageausdrücken werden in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verschiedene Ausdrucksarten bereitgestellt, darunter Konstanten, Variablen, Funktionen, Konstruktoren und relationale Standardoperatoren, wie z. B. Filter und Join.</span><span class="sxs-lookup"><span data-stu-id="4b254-115">Several kinds of expressions are provided by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] for composing query expressions, including constants, variables, functions, constructors, and standard relational operators like filter and join.</span></span> <span data-ttu-id="4b254-116">Jedes DbExpression-Objekt verfügt über eine ResultType-Eigenschaft, die den Typ des von diesem Ausdruck erzeugten Ergebnisses darstellt.</span><span class="sxs-lookup"><span data-stu-id="4b254-116">Every DbExpression object has a ResultType property that represents the type of the result produced by that expression.</span></span> <span data-ttu-id="4b254-117">Dieser Typ wird als "TypeUsage" ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="4b254-117">This type is expressed as a TypeUsage.</span></span>

## <a name="shapes-of-the-output-query-command-tree"></a><span data-ttu-id="4b254-118">Formen der Ausgabeabfrage-Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="4b254-118">Shapes of the Output Query Command Tree</span></span>

<span data-ttu-id="4b254-119">Ausgabeabfrage-Befehlsstrukturen entsprechen relationalen (SQL-)Abfragen und unterliegen weitaus strengeren Regeln als Abfragebefehlsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="4b254-119">Output query command trees closely represent relational (SQL) queries and adhere to much stricter rules than those that apply to query command trees.</span></span> <span data-ttu-id="4b254-120">In der Regel enthalten sie Konstrukte, die einfach in SQL übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4b254-120">They typically contain constructs that are easily translated to SQL.</span></span>

<span data-ttu-id="4b254-121">Eingabebefehlsstrukturen werden für das konzeptionelle Modell ausgedrückt, das Navigationseigenschaften, Zuordnungen zwischen Entitäten und Vererbung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b254-121">Input command trees are expressed against the conceptual model, which supports navigation properties, associations among entities, and inheritance.</span></span> <span data-ttu-id="4b254-122">Ausgabebefehlsstrukturen werden für das Speichermodell ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="4b254-122">Output command trees are expressed against the storage model.</span></span> <span data-ttu-id="4b254-123">Mit Eingabebefehlsstrukturen können geschachtelte Auflistungen projiziert werden, nicht jedoch mit Ausgabebefehlsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="4b254-123">Input command trees allow you to project nested collections, but output command trees do not.</span></span>

<span data-ttu-id="4b254-124">Ausgabeabfrage-Befehlsstrukturen beruhen auf einer Teilmenge der verfügbaren "DbExpression"-Objekte. Selbst einige der Ausdrücke dieser Teilmenge unterliegen einer eingeschränkten Verwendung.</span><span class="sxs-lookup"><span data-stu-id="4b254-124">Output query command trees are built using a subset of the available DbExpression objects and even some expressions in that subset have restricted usage.</span></span>

<span data-ttu-id="4b254-125">Typvorgänge, wie z. B. das Überprüfen, ob es sich bei einem angegebenen Ausdruck um einen bestimmten Typ handelt, oder das Filtern von Sätzen anhand eines Typs, sind in Ausgabebefehlsstrukturen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4b254-125">Type operations, like checking whether a given expression is of a particular type or filtering sets based on a type, are not present in output command trees.</span></span>

<span data-ttu-id="4b254-126">In Ausgabebefehlsstrukturen werden für Projektionen nur Ausdrücke verwendet, die boolesche Werte zurückgeben. Dies gilt nur für Prädikate in Ausdrücken, die ein Prädikat, wie z. B. eine Filter- oder eine Case-Anweisung erfordern.</span><span class="sxs-lookup"><span data-stu-id="4b254-126">In output command trees, only expressions that return Boolean values are used for projections and only for predicates in expressions requiring a predicate, like a filter or a case statement.</span></span>

<span data-ttu-id="4b254-127">Der Stamm einer Ausgabeabfrage-Befehlsstruktur ist ein "DbProjectExpression"-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b254-127">The root of an output query command trees is a DbProjectExpression object.</span></span>

### <a name="expression-types-not-present-in-output-query-command-trees"></a><span data-ttu-id="4b254-128">Nicht in Ausgabeabfrage-Befehlsstrukturen vorhandene Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4b254-128">Expression Types Not Present in Output Query Command Trees</span></span>

<span data-ttu-id="4b254-129">Die folgenden Ausdruckstypen sind in einer Ausgabeabfrage-Befehlsstruktur nicht gültig und müssen nicht von Anbietern behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="4b254-129">The following expression types are not valid in an output query command tree and do not need to be handled by providers:</span></span>

- <span data-ttu-id="4b254-130">DbDerefExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-130">DbDerefExpression</span></span>

- <span data-ttu-id="4b254-131">DbEntityRefExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-131">DbEntityRefExpression</span></span>

- <span data-ttu-id="4b254-132">DbRefKeyExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-132">DbRefKeyExpression</span></span>

- <span data-ttu-id="4b254-133">DbIsOfExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-133">DbIsOfExpression</span></span>

- <span data-ttu-id="4b254-134">DbOfTypeExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-134">DbOfTypeExpression</span></span>

- <span data-ttu-id="4b254-135">DbRefExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-135">DbRefExpression</span></span>

- <span data-ttu-id="4b254-136">DbRelationshipNavigationExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-136">DbRelationshipNavigationExpression</span></span>

- <span data-ttu-id="4b254-137">DbTreatExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-137">DbTreatExpression</span></span>

### <a name="expression-restrictions-and-notes"></a><span data-ttu-id="4b254-138">Ausdruckseinschränkungen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b254-138">Expression Restrictions and Notes</span></span>

<span data-ttu-id="4b254-139">Viele Ausdrücke können nur eingeschränkt in Ausgabeabfrage-Befehlsstrukturen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="4b254-139">Many expressions can only be used in a restricted manner in output query command trees:</span></span>

#### <a name="dbfunctionexpression"></a><span data-ttu-id="4b254-140">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-140">DbFunctionExpression</span></span>

<span data-ttu-id="4b254-141">Die folgenden Funktionstypen können übergeben werden:</span><span class="sxs-lookup"><span data-stu-id="4b254-141">The following function types can be passed:</span></span>

- <span data-ttu-id="4b254-142">Kanonische Funktionen, die vom EDM-Namespace erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="4b254-142">Canonical functions that are recognized by the Edm namespace.</span></span>

- <span data-ttu-id="4b254-143">Integrierte (Speicher-)Funktionen, die von "BuiltInAttribute" erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="4b254-143">Built-in (store) functions that are recognized by the BuiltInAttribute.</span></span>

- <span data-ttu-id="4b254-144">Benutzerdefinierte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4b254-144">User-defined functions.</span></span>

<span data-ttu-id="4b254-145">Kanonische Funktionen (Weitere Informationen finden Sie unter [kanonische Funktionen](./language-reference/canonical-functions.md) ) werden als Teil [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]von angegeben, und Anbieter sollten auf der Grundlage dieser Spezifikationen Implementierungen für kanonische Funktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4b254-145">Canonical functions (see [Canonical Functions](./language-reference/canonical-functions.md) for more information) are specified as part of the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], and providers should supply implementations for canonical functions based on those specifications.</span></span> <span data-ttu-id="4b254-146">Speicherfunktionen beruhen auf den Spezifikationen des entsprechenden Anbietermanifests.</span><span class="sxs-lookup"><span data-stu-id="4b254-146">Store functions are based on the specifications in the corresponding provider manifest.</span></span> <span data-ttu-id="4b254-147">Benutzerdefinierte Funktionen beruhen auf den SSDL-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="4b254-147">User defined functions are based on specifications in the SSDL.</span></span>

<span data-ttu-id="4b254-148">Zudem verfügen Funktionen mit dem "NiladicFunction"-Attribut nicht über Argumente und sollten ohne die Klammer am Ende übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4b254-148">Also, functions having the NiladicFunction attribute have no arguments and should be translated without the parenthesis at the end.</span></span>  <span data-ttu-id="4b254-149">Das heißt,  *\<dass FunctionName >* anstelle von  *\<FunctionName > ()* ist.</span><span class="sxs-lookup"><span data-stu-id="4b254-149">That is, to *\<functionName>* instead of *\<functionName>()*.</span></span>

#### <a name="dbnewinstanceexpression"></a><span data-ttu-id="4b254-150">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-150">DbNewInstanceExpression</span></span>

<span data-ttu-id="4b254-151">"DbNewInstanceExpression" kann nur in den folgenden beiden Fällen auftreten:</span><span class="sxs-lookup"><span data-stu-id="4b254-151">DbNewInstanceExpression can only occur in the following two cases:</span></span>

- <span data-ttu-id="4b254-152">Als Projektionseigenschaft von "DbProjectExpression".</span><span class="sxs-lookup"><span data-stu-id="4b254-152">As the Projection property of DbProjectExpression.</span></span>  <span data-ttu-id="4b254-153">Bei dieser Verwendungsart gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="4b254-153">When used as such the following restrictions apply:</span></span>

  - <span data-ttu-id="4b254-154">Der Ergebnistyp muss ein Zeilentyp sein.</span><span class="sxs-lookup"><span data-stu-id="4b254-154">The result type must be a row type.</span></span>

  - <span data-ttu-id="4b254-155">Bei allen Argumenten handelt es sich um einen Ausdruck, der ein Ergebnis mit einem primitiven Typ erzeugt.</span><span class="sxs-lookup"><span data-stu-id="4b254-155">Each of its arguments is an expression that produces a result with a primitive type.</span></span> <span data-ttu-id="4b254-156">In der Regel handelt es sich bei allen Argumenten um Skalarausdrücke, wie z. B. ein "PropertyExpression" über einem "DbVariableReferenceExpression", ein Funktionsaufruf oder eine arithmetische Berechnung von "DbPropertyExpression" über einem "DbVariableReferenceExpression" oder über einem Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="4b254-156">Typically, each argument is a scalar expression, like a PropertyExpression over a DbVariableReferenceExpression, a function invocation, or an arithmetic computation of the DbPropertyExpression over a DbVariableReferenceExpression or a function invocation.</span></span> <span data-ttu-id="4b254-157">In der Liste der Argumente für einen "DbNewInstanceExpression" können jedoch auch Ausdrücke auftreten, bei denen es sich um skalare Unterabfragen handelt.</span><span class="sxs-lookup"><span data-stu-id="4b254-157">However, an expression representing a scalar subquery can also occur in the list of arguments for a DbNewInstanceExpression.</span></span> <span data-ttu-id="4b254-158">Ein Ausdruck, der eine skalare Unterabfrage darstellt, ist eine Ausdrucks Baumstruktur, die eine Unterabfrage darstellt, die genau eine Zeile und eine Spalte eines primitiven Typs mit einem "DbElementExpression"-Objekt Stamm zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4b254-158">An expression that represents a scalar subquery is an expression tree that represents a subquery that returns exactly one row and one column of a primitive type with a DbElementExpression object root</span></span>

- <span data-ttu-id="4b254-159">Mit einem Auflistungsrückgabetyp. In diesem Fall wird eine neue Auflistung der als Argumente bereitgestellten Ausdrücke definiert.</span><span class="sxs-lookup"><span data-stu-id="4b254-159">With a collection return type, in which case it defines a new collection of the expressions provided as arguments.</span></span>

#### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="4b254-160">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-160">DbVariableReferenceExpression</span></span>

<span data-ttu-id="4b254-161">Bei einem "DbVariableReferenceExpression" muss es sich um ein untergeordnetes Element des Knotens "DbPropertyExpression" handeln.</span><span class="sxs-lookup"><span data-stu-id="4b254-161">A DbVariableReferenceExpression has to be a child of DbPropertyExpression node.</span></span>

#### <a name="dbgroupbyexpression"></a><span data-ttu-id="4b254-162">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-162">DbGroupByExpression</span></span>

<span data-ttu-id="4b254-163">Die Aggregateigenschaft eines "DbGroupByExpression" kann nur über Elemente des Typs "DbFunctionAggregate" verfügen.</span><span class="sxs-lookup"><span data-stu-id="4b254-163">The Aggregates property of a DbGroupByExpression can only have elements of type DbFunctionAggregate.</span></span> <span data-ttu-id="4b254-164">Es gibt keine anderen Aggregattypen.</span><span class="sxs-lookup"><span data-stu-id="4b254-164">There are no other aggregate types.</span></span>

#### <a name="dblimitexpression"></a><span data-ttu-id="4b254-165">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-165">DbLimitExpression</span></span>

<span data-ttu-id="4b254-166">Bei der "Limit"-Eigenschaft kann es sich nur um einen "DbConstantExpression" oder einen "DbParameterReferenceExpression" handeln.</span><span class="sxs-lookup"><span data-stu-id="4b254-166">The property Limit can only be a DbConstantExpression or a DbParameterReferenceExpression.</span></span> <span data-ttu-id="4b254-167">Ab Version 3.5 von .NET Framework gilt für die "WithTies"-Eigenschaft immer der Wert "false".</span><span class="sxs-lookup"><span data-stu-id="4b254-167">Also property WithTies is always false as of version 3.5 of the .NET Framework.</span></span>

#### <a name="dbscanexpression"></a><span data-ttu-id="4b254-168">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="4b254-168">DbScanExpression</span></span>

<span data-ttu-id="4b254-169">Bei Verwendung in Ausgabe Befehlsstrukturen stellt DbScanExpression einen Scan über eine Tabelle, eine Sicht oder eine Speicher Abfrage dar, die durch EntitySetBase:: Target dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b254-169">When used in output command trees, the DbScanExpression effectively represents a scan over a table, a view, or a store query, represented by EntitySetBase::Target.</span></span>

<span data-ttu-id="4b254-170">Wenn die Metadateneigenschaft "definierende Abfrage" des Ziels nicht NULL ist, stellt Sie eine Abfrage dar. der Abfragetext, für den in der Metadateneigenschaft in der spezifischen Sprache des Anbieters (oder im Dialekt) bereitgestellt wird, wie in der Speicher Schema Definition angegeben.</span><span class="sxs-lookup"><span data-stu-id="4b254-170">If the metadata property "Defining Query" of the target is non-null, then it represents a query, the query text for which is provided in that metadata property in the provider’s specific language (or dialect) as specified in the store schema definition.</span></span>

<span data-ttu-id="4b254-171">Andernfalls entspricht das Ziel einer Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="4b254-171">Otherwise, the target represents a table or a view.</span></span> <span data-ttu-id="4b254-172">Das Schema Präfix ist entweder in der Metadateneigenschaft "Schema", wenn nicht NULL, andernfalls der Name des Entitätencontainers.</span><span class="sxs-lookup"><span data-stu-id="4b254-172">Its schema prefix is either in the "Schema" metadata property, if not null, otherwise is the entity container name.</span></span>  <span data-ttu-id="4b254-173">Der Tabellen-oder Sichtname ist entweder die Metadateneigenschaft "Table", wenn Sie nicht NULL ist, andernfalls die Name-Eigenschaft der Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="4b254-173">The table or view name is either the "Table" metadata property, if not null, otherwise the Name property of the entity set base.</span></span>

<span data-ttu-id="4b254-174">All diese Eigenschaften beruhen auf der Definition des entsprechenden "EntitySet" in der Speicherschema-Definitionsdatei (SSDL).</span><span class="sxs-lookup"><span data-stu-id="4b254-174">All these properties originate from the definition of the corresponding EntitySet in the store schema definition file (the SSDL).</span></span>

### <a name="using-primitive-types"></a><span data-ttu-id="4b254-175">Verwenden primitiver Typen</span><span class="sxs-lookup"><span data-stu-id="4b254-175">Using Primitive Types</span></span>

<span data-ttu-id="4b254-176">Wenn in Ausgabebefehlsstrukturen auf primitive Typen verwiesen wird, erfolgt der Verweis in der Regel anhand der primitiven Typen des konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="4b254-176">When primitive types are referenced in output command trees, they are typically referenced in the conceptual model's primitive types.</span></span> <span data-ttu-id="4b254-177">Für bestimmte Ausdrücke benötigen die Anbieter jedoch den entsprechenden primitiven Speichertyp.</span><span class="sxs-lookup"><span data-stu-id="4b254-177">However, for certain expressions, providers need the corresponding store primitive type.</span></span> <span data-ttu-id="4b254-178">Beispiele für solche Ausdrücke sind "DbCastExpression" und möglicherweise "DbNullExpression", sofern der Anbieter für den entsprechenden Typ NULL umwandeln muss.</span><span class="sxs-lookup"><span data-stu-id="4b254-178">Examples of such expressions include DbCastExpression and possibly DbNullExpression, if the provider needs to cast the null to the corresponding type.</span></span> <span data-ttu-id="4b254-179">In solchen Fällen sollten Anbieter die Zuordnung zum Anbietertyp anhand der Art des primitiven Typs und dessen Facets vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4b254-179">In these cases, providers should do the mapping to the provider type based on the primitive type kind and its facets.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b254-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b254-180">See also</span></span>

- [<span data-ttu-id="4b254-181">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="4b254-181">SQL Generation</span></span>](sql-generation.md)
