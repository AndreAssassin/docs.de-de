---
title: Funktionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: f31f829b53160da5a043617b9aa999b398859f17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034163"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="25fc4-102">Funktionen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="25fc4-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="25fc4-103">Entity SQL unterstützt benutzerdefinierte Funktionen sowie kanonische und anbieterspezifische Funktionen.</span><span class="sxs-lookup"><span data-stu-id="25fc4-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="25fc4-104">Benutzerdefinierte Funktionen werden im konzeptionellen Modell oder inline in der Abfrage angegeben.</span><span class="sxs-lookup"><span data-stu-id="25fc4-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="25fc4-105">Weitere Informationen finden Sie unter [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="25fc4-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="25fc4-106">Kanonische Funktionen sind im Entity Framework vordefiniert und müssen von Datenanbietern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="25fc4-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="25fc4-107">Entity SQL-Befehle schlagen fehl, wenn ein Benutzer eine Funktion aufruft, die von einem Anbieter nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="25fc4-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="25fc4-108">Deshalb werden kanonische Funktionen im Allgemeinen speicherspezifischen Funktionen vorgezogen, die sich in einem anbieterspezifischen Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="25fc4-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="25fc4-109">Weitere Informationen finden Sie unter [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="25fc4-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="25fc4-110">Der verwaltete Anbieter des Microsoft SQL Client stellt eine Reihe anbieterspezifischer Funktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="25fc4-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="25fc4-111">Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="25fc4-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25fc4-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="25fc4-112">In This Section</span></span>  
 [<span data-ttu-id="25fc4-113">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="25fc4-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="25fc4-114">Auflösung von Funktionsüberladungen</span><span class="sxs-lookup"><span data-stu-id="25fc4-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="25fc4-115">Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="25fc4-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="25fc4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25fc4-116">See also</span></span>

- [<span data-ttu-id="25fc4-117">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="25fc4-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
