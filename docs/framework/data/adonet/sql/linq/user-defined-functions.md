---
title: Benutzerdefinierte Funktionen
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: fb55a8b248b085275f83d47b1f452cd07bd8dcb1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582641"
---
# <a name="user-defined-functions"></a><span data-ttu-id="f71ea-102">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="f71ea-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="f71ea-103">verwendet Methoden in Ihrem Objektmodell, die benutzerdefinierte Funktionen darstellen.</span><span class="sxs-lookup"><span data-stu-id="f71ea-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="f71ea-104">Sie definieren die Methoden als Funktionen, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf auch das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="f71ea-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="f71ea-105">Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="f71ea-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="f71ea-106">Zur Vermeidung einer <xref:System.InvalidOperationException> müssen benutzerdefinierte Funktionen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in einer der folgenden Formen vorliegen:</span><span class="sxs-lookup"><span data-stu-id="f71ea-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="f71ea-107">Eine als Methodenaufruf eingebundene Funktion, die über die richtigen Zuordnungsattribute verfügt.</span><span class="sxs-lookup"><span data-stu-id="f71ea-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="f71ea-108">Weitere Informationen finden Sie unter [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="f71ea-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="f71ea-109">Eine spezifische statische SQL-Methode für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f71ea-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="f71ea-110">Eine Funktion, die von einer .NET Framework-Methode unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f71ea-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="f71ea-111">Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="f71ea-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="f71ea-112">Entwickler, die mit Visual Studio normalerweise verwenden die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] , benutzerdefinierte Funktionen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f71ea-112">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f71ea-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f71ea-113">In This Section</span></span>  
 [<span data-ttu-id="f71ea-114">Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="f71ea-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="f71ea-115">Beschreibt, wie eine Funktion, die Skalarwerte zurückgibt, implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f71ea-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="f71ea-116">Vorgehensweise: Verwenden von benutzerdefinierten Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="f71ea-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="f71ea-117">Beschreibt, wie eine Funktion, die Tabellenwerte zurückgibt, implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f71ea-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="f71ea-118">Vorgehensweise: Benutzerdefinierte Funktionen Inline aufrufen</span><span class="sxs-lookup"><span data-stu-id="f71ea-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="f71ea-119">Erläutert Inline-Funktionsaufrufe und die Ausführungsunterschiede, wenn der Aufruf inline erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f71ea-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
