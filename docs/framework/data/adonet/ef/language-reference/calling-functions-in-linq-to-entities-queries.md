---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251264"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="bb061-102">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="bb061-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="bb061-103">In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bb061-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="bb061-104">Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="bb061-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="bb061-105">Weitere Informationen finden Sie unter [Vorgehensweise: Kanonische Funktionen](how-to-call-canonical-functions.md) und [Gewusst wie: Ruft Daten Bank](how-to-call-database-functions.md)Funktionen auf.</span><span class="sxs-lookup"><span data-stu-id="bb061-105">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="bb061-106">Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="bb061-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="bb061-107">Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb061-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="bb061-108">Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.</span><span class="sxs-lookup"><span data-stu-id="bb061-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="bb061-109">Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="bb061-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="bb061-110">Weitere Informationen hierzu finden Sie in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="bb061-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb061-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bb061-111">In This Section</span></span>  
 [<span data-ttu-id="bb061-112">Vorgehensweise: Kanonische Funktionen aufzurufen</span><span class="sxs-lookup"><span data-stu-id="bb061-112">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="bb061-113">Vorgehensweise: Datenbankfunktionen aufzurufen</span><span class="sxs-lookup"><span data-stu-id="bb061-113">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="bb061-114">Vorgehensweise: Benutzerdefinierte Datenbankfunktionen aufzurufen</span><span class="sxs-lookup"><span data-stu-id="bb061-114">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="bb061-115">Vorgehensweise: Modell definierte Funktionen in Abfragen abrufen</span><span class="sxs-lookup"><span data-stu-id="bb061-115">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="bb061-116">Vorgehensweise: Aufgerufen Modell definierter Funktionen als Objektmethoden</span><span class="sxs-lookup"><span data-stu-id="bb061-116">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb061-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb061-117">See also</span></span>

- [<span data-ttu-id="bb061-118">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bb061-118">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="bb061-119">Canonical Functions (Kanonische Funktionen)</span><span class="sxs-lookup"><span data-stu-id="bb061-119">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="bb061-120">[Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb061-120">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="bb061-121">[Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb061-121">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
