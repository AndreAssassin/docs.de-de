---
title: 'Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (C#)'
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: 034a391a21e685a6ceb8342bb1738ff34381cebb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598045"
---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="737f2-102">Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="737f2-102">How to: Execute Expression Trees (C#)</span></span>
<span data-ttu-id="737f2-103">In diesem Thema erfahren Sie, wie eine Ausdrucksbaumstruktur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="737f2-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="737f2-104">Die Ausführung einer Ausdrucksbaumstruktur gibt möglicherweise einen Wert zurück. Es kann jedoch auch nur eine Aktion ausgeführt werden, z.B. das Aufrufen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="737f2-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="737f2-105">Nur Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="737f2-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="737f2-106">Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, sind vom Typ <xref:System.Linq.Expressions.LambdaExpression> oder <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="737f2-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="737f2-107">Um diese Ausdrucksbaumstruktur auszuführen, rufen Sie die <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>-Methode auf, um einen ausführbaren Delegaten zu erstellen und diesen anschließend aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="737f2-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="737f2-108">Wenn der Typ des Delegaten nicht bekannt ist, d.h. wenn der Lambdaausdruck vom Typ <xref:System.Linq.Expressions.LambdaExpression> und nicht <xref:System.Linq.Expressions.Expression%601> ist, müssen Sie die <xref:System.Delegate.DynamicInvoke%2A>-Methode auf dem Delegaten aufrufen, anstatt sie direkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="737f2-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="737f2-109">Wenn eine Ausdrucksbaumstruktur keinen Lambdaausdruck darstellt,können Sie einen neuen Lambdaausdruck erstellen, der die ursprüngliche Ausdrucksbaumstruktur als Textkörper hat, indem Sie die <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="737f2-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="737f2-110">Anschließend können Sie den Lambdaausdruck ausführen, wie weiter oben in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="737f2-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="737f2-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="737f2-111">Example</span></span>  
 <span data-ttu-id="737f2-112">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur ausgeführt wird, die das Potenzieren darstellt, indem ein Lambdaausdruck erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="737f2-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="737f2-113">Das Ergebnis, das die potenzierte Zahl darstellt, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="737f2-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="737f2-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="737f2-114">Compiling the Code</span></span>  
  
- <span data-ttu-id="737f2-115">Fügen Sie einen Projektverweis auf „System.Core.dll“ hinzu, wenn nicht bereits darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="737f2-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
- <span data-ttu-id="737f2-116">Binden Sie den System.Linq.Expressions-Namespace ein.</span><span class="sxs-lookup"><span data-stu-id="737f2-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737f2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="737f2-117">See also</span></span>

- [<span data-ttu-id="737f2-118">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="737f2-118">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="737f2-119">Vorgehensweise: Ändern von Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="737f2-119">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
