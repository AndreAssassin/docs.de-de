---
title: Where-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945209"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="3675c-102">Where-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3675c-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="3675c-103">Gibt die filterbedingung für eine Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="3675c-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3675c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3675c-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="3675c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3675c-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="3675c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3675c-106">Required.</span></span> <span data-ttu-id="3675c-107">Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Output-Auflistung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3675c-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="3675c-108">Muss der Ausdruck ausgewertet, um eine `Boolean` Wert oder die Darstellung einer `Boolean` Wert.</span><span class="sxs-lookup"><span data-stu-id="3675c-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="3675c-109">Wenn das Ergebnis der bedingungsauswertung `True`, das Element im Resultset Abfrage enthalten, andernfalls das Element wird aus dem Abfrageergebnis ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3675c-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3675c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3675c-110">Remarks</span></span>  
 <span data-ttu-id="3675c-111">Die `Where` -Klausel ermöglichen es Ihnen, Abfragen von Daten zu filtern, dazu nur Elemente, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3675c-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="3675c-112">Elemente, deren Werte bewirken, dass, die `Where` Klausel ergibt `True` befinden sich im Resultset Abfrage; andere Elemente ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3675c-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="3675c-113">Der Ausdruck, der verwendet wird eine `Where` Klausel ergeben muss eine `Boolean` oder die Entsprechung von einer `Boolean`, z. B. eine ganze Zahl, der ergibt `False` Wenn der Wert 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="3675c-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="3675c-114">Sie können in mehrere Ausdrücke kombinieren einer `Where` Klausel, indem Sie logische Operatoren wie z. B. `And`, `Or`, `AndAlso`, `OrElse`, `Is`, und `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="3675c-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="3675c-115">In der Standardeinstellung Abfrageausdrücke werden erst ausgewertet, darauf zugegriffen wird, z. B. Wenn sie sind datengebunden oder durchlaufen in einer `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="3675c-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="3675c-116">Daher die `Where` Klausel wird nicht ausgewertet, bis die Abfrage zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="3675c-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="3675c-117">Wenn Sie die Werte für die Abfrage, die verwendet werden extern haben die `Where` -Klausel, stellen Sie sicher, dass der entsprechende Wert, in verwendet wird der `Where` Klausel, die zum Zeitpunkt der Ausführung der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="3675c-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="3675c-118">Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="3675c-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="3675c-119">Sie können Funktionen aufrufen einer `Where` -Klausel, um eine Berechnung oder Operation auf einen Wert aus dem aktuellen Element in der Auflistung ausführen.</span><span class="sxs-lookup"><span data-stu-id="3675c-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="3675c-120">Aufrufen einer Funktion in einer `Where` Klausel kann dazu führen, dass die Abfrage ausgeführt werden, sofort wenn er nicht definiert wird, wenn darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="3675c-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="3675c-121">Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="3675c-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3675c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3675c-122">Example</span></span>  
 <span data-ttu-id="3675c-123">Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` -Objekt in der `customers` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="3675c-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="3675c-124">Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="3675c-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="3675c-125">Die `For Each` -Schleife zeigt den Firmennamen für jeden Kunden in den Abfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="3675c-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="3675c-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3675c-126">Example</span></span>  
 <span data-ttu-id="3675c-127">Im folgenden Beispiel wird `And` und `Or` logische Operatoren in der `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="3675c-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="3675c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3675c-128">See also</span></span>

- [<span data-ttu-id="3675c-129">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3675c-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="3675c-130">Abfragen</span><span class="sxs-lookup"><span data-stu-id="3675c-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3675c-131">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="3675c-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="3675c-132">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="3675c-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="3675c-133">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3675c-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
