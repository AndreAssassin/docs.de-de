---
title: 'Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
ms.openlocfilehash: d7e0f5f6687ffb4293209a29279ca16361e7424e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642331"
---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="b8206-102">Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8206-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="b8206-103">In diesem Thema erfahren Sie, wie eine Ausdrucksbaumstruktur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b8206-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="b8206-104">Die Ausführung einer Ausdrucksbaumstruktur gibt möglicherweise einen Wert zurück. Es kann jedoch auch nur eine Aktion ausgeführt werden, z.B. das Aufrufen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="b8206-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="b8206-105">Nur Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b8206-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="b8206-106">Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, sind vom Typ <xref:System.Linq.Expressions.LambdaExpression> oder <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="b8206-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="b8206-107">Um diese Ausdrucksbaumstruktur auszuführen, rufen Sie die <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>-Methode auf, um einen ausführbaren Delegaten zu erstellen und diesen anschließend aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b8206-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8206-108">Wenn der Typ des Delegaten nicht bekannt ist, d.h. wenn der Lambdaausdruck vom Typ <xref:System.Linq.Expressions.LambdaExpression> und nicht <xref:System.Linq.Expressions.Expression%601> ist, müssen Sie die <xref:System.Delegate.DynamicInvoke%2A>-Methode auf dem Delegaten aufrufen, anstatt sie direkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b8206-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="b8206-109">Wenn eine Ausdrucksbaumstruktur keinen Lambdaausdruck darstellt,können Sie einen neuen Lambdaausdruck erstellen, der die ursprüngliche Ausdrucksbaumstruktur als Textkörper hat, indem Sie die <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b8206-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="b8206-110">Anschließend können Sie den Lambdaausdruck ausführen, wie weiter oben in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8206-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8206-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8206-111">Example</span></span>  
 <span data-ttu-id="b8206-112">Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur ausgeführt wird, die das Potenzieren darstellt, indem ein Lambdaausdruck erstellt und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b8206-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="b8206-113">Das Ergebnis, das die potenzierte Zahl darstellt, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8206-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8206-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b8206-114">Compiling the Code</span></span>  
  
- <span data-ttu-id="b8206-115">Fügen Sie einen Projektverweis auf „System.Core.dll“ hinzu, wenn nicht bereits darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b8206-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
- <span data-ttu-id="b8206-116">Binden Sie den System.Linq.Expressions-Namespace ein.</span><span class="sxs-lookup"><span data-stu-id="b8206-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8206-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8206-117">See also</span></span>

- [<span data-ttu-id="b8206-118">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8206-118">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="b8206-119">Vorgehensweise: Ändern von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8206-119">How to: Modify Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
