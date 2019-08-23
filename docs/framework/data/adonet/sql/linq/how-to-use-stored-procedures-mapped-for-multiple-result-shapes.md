---
title: 'Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 22614be8e53d975c4efdf7004f41906c58639c61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938698"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a><span data-ttu-id="53b96-102">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="53b96-102">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>
<span data-ttu-id="53b96-103">Wenn eine gespeicherte Prozedur mehrere Ergebnisformen zurückgeben kann, lässt sich der Rückgabetyp nicht auf eine einzige Projektionsform festlegen.</span><span class="sxs-lookup"><span data-stu-id="53b96-103">When a stored procedure can return multiple result shapes, the return type cannot be strongly typed to a single projection shape.</span></span> <span data-ttu-id="53b96-104">Obwohl [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] alle möglichen Projektions Typen generieren kann, ist die Reihenfolge, in der Sie zurückgegeben werden, nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="53b96-104">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can generate all possible projection types, it cannot know the order in which they will be returned.</span></span>  
  
 <span data-ttu-id="53b96-105">Vergleichen Sie dieses Szenario mit gespeicherten Prozeduren, die sequenziell mehrere Ergebnisformen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="53b96-105">Contrast this scenario with stored procedures that produce multiple result shapes sequentially.</span></span> <span data-ttu-id="53b96-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)sequenziellen Ergebnis Formen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="53b96-106">For more information, see [How to: Use Stored Procedures Mapped for Sequential Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span></span>  
  
 <span data-ttu-id="53b96-107">Das <xref:System.Data.Linq.Mapping.ResultTypeAttribute>-Attribut wird auf gespeicherte Prozeduren angewendet, die mehrere Ergebnistypen zurückgeben, um den Typsatz anzugeben, den die Prozedur zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="53b96-107">The <xref:System.Data.Linq.Mapping.ResultTypeAttribute> attribute is applied to stored procedures that return multiple result types to specify the set of types the procedure can return.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b96-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53b96-108">Example</span></span>  
 <span data-ttu-id="53b96-109">Im folgenden SQL-Codebeispiel hängt die Ergebnisform von der Eingabe ab (`shape =1` oder `shape = 2`).</span><span class="sxs-lookup"><span data-stu-id="53b96-109">In the following SQL code example, the result shape depends on the input (`shape =1` or `shape = 2`).</span></span> <span data-ttu-id="53b96-110">Es ist nicht bekannt, welche Projektion zuerst zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="53b96-110">You do not know which projection will be returned first.</span></span>  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="53b96-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53b96-111">Example</span></span>  
 <span data-ttu-id="53b96-112">Um die gespeicherte Prozedur auszuführen, wird in etwa der folgende Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="53b96-112">You would use code similar to the following to execute this stored procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53b96-113">Sie müssen mithilfe Ihrer Kenntnisse über die gespeicherte Prozedur das <xref:System.Data.Linq.IMultipleResults.GetResult%2A>-Muster verwenden, um einen Enumerator mit dem richtigen Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="53b96-113">You must use the <xref:System.Data.Linq.IMultipleResults.GetResult%2A> pattern to obtain an enumerator of the correct type, based on your knowledge of the stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="53b96-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53b96-114">See also</span></span>

- [<span data-ttu-id="53b96-115">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="53b96-115">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
