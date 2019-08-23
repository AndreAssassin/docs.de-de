---
title: SqlClient für Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: ec67637c416f2560c1f5d0a9fd0e856703820a84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69954972"
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="87f45-102">SqlClient für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="87f45-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="87f45-103">Dieser Abschnitt beschreibt den .NET Framework-Datenanbieter für SQL Server (SqlClient), der dem Entity Framework die Arbeit mit Microsoft SQL Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="87f45-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="87f45-104">Anbieterschemaattribut</span><span class="sxs-lookup"><span data-stu-id="87f45-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="87f45-105">`Provider` ist ein Attribut des `Schema`-Elements der Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL).</span><span class="sxs-lookup"><span data-stu-id="87f45-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="87f45-106">Um SqlClient zu verwenden, weisen Sie dem `Provider`-Attribut des `Schema`-Elements die Zeichenfolge "System.Data.SqlClient" zu.</span><span class="sxs-lookup"><span data-stu-id="87f45-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="87f45-107">'ProviderManifestToken'-Schemaattribut</span><span class="sxs-lookup"><span data-stu-id="87f45-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="87f45-108">Das `ProviderManifestToken`-Element ist ein erforderliches Attribut des `Schema`-Elements.</span><span class="sxs-lookup"><span data-stu-id="87f45-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="87f45-109">Dieses Token wird verwendet, um das Anbietermanifest für Offlineszenarien zu laden.</span><span class="sxs-lookup"><span data-stu-id="87f45-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="87f45-110">Weitere Informationen `ProviderManifestToken` zum-Attribut finden Sie unter [Schema-Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="87f45-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).</span></span>  
  
 <span data-ttu-id="87f45-111">SqlClient kann als Datenanbieter für verschiedene Versionen von SQL Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87f45-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="87f45-112">Diese Versionen haben verschiedene Funktionen.</span><span class="sxs-lookup"><span data-stu-id="87f45-112">These versions have different capabilities.</span></span> <span data-ttu-id="87f45-113">Beispielsweise unterstützt `varchar(max)` SQL Server 2000 nicht die Typen und `nvarchar(max)` , die mit SQL Server 2005 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="87f45-113">For example, SQL Server 2000 does not support `varchar(max)` and `nvarchar(max)` types that were introduced with SQL Server 2005.</span></span>  
  
 <span data-ttu-id="87f45-114">SqlClient erzeugt und akzeptiert die folgenden Anbietermanifesttoken für die verschiedenen Versionen von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87f45-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="87f45-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="87f45-115">SQL Server 2000</span></span>|<span data-ttu-id="87f45-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="87f45-116">SQL Server 2005</span></span>|<span data-ttu-id="87f45-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="87f45-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="87f45-118">2000</span><span class="sxs-lookup"><span data-stu-id="87f45-118">2000</span></span>|<span data-ttu-id="87f45-119">2005</span><span class="sxs-lookup"><span data-stu-id="87f45-119">2005</span></span>|<span data-ttu-id="87f45-120">2008</span><span class="sxs-lookup"><span data-stu-id="87f45-120">2008</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="87f45-121">Ab Visual Studio 2010 unterstützen die [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) SQL Server 2000 nicht.</span><span class="sxs-lookup"><span data-stu-id="87f45-121">Starting with Visual Studio 2010, the [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="87f45-122">Anbieternamespacename</span><span class="sxs-lookup"><span data-stu-id="87f45-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="87f45-123">Alle Anbieter müssen einen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="87f45-123">All providers must specify a namespace.</span></span> <span data-ttu-id="87f45-124">Anhand dieser Eigenschaft ermittelt Entity Framework, welches Präfix von diesem Anbieter für spezifische Konstrukte wie Typen und Funktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87f45-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="87f45-125">Der Namespace für SqlClient-Anbietermanifeste lautet `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="87f45-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="87f45-126">Weitere Informationen zu Namespaces finden Sie unter [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="87f45-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="87f45-127">Typen</span><span class="sxs-lookup"><span data-stu-id="87f45-127">Types</span></span>  
 <span data-ttu-id="87f45-128">Der SqlClient-Anbieter für das Entity Framework stellt Zuordnungsinformationen zwischen Typen des konzeptionellen Modells und SQL Server-Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="87f45-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="87f45-129">Weitere Informationen finden Sie unter [SqlClient für Entity frameworktypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="87f45-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="87f45-130">Funktionen</span><span class="sxs-lookup"><span data-stu-id="87f45-130">Functions</span></span>  
 <span data-ttu-id="87f45-131">Der SqlClient-Anbieter für das Entity Framework definiert die Liste der vom Anbieter unterstützten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="87f45-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="87f45-132">Eine Liste der unterstützten Funktionen finden Sie unter [SqlClient für Entity Framework Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="87f45-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87f45-133">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="87f45-133">In This Section</span></span>  
 [<span data-ttu-id="87f45-134">SqlClient für Entity Framework-Funktionen</span><span class="sxs-lookup"><span data-stu-id="87f45-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="87f45-135">SqlClient für Entity Framework-Typen</span><span class="sxs-lookup"><span data-stu-id="87f45-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="87f45-136">Bekannte Probleme in SqlClient für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="87f45-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="87f45-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f45-137">See also</span></span>

- [<span data-ttu-id="87f45-138">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="87f45-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="87f45-139">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="87f45-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [<span data-ttu-id="87f45-140">Bekannte Probleme im SqlClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="87f45-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
