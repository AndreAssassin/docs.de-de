---
title: 'Vorgehensweise: Ändern von Ausdrucksbaumstrukturen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: a9b94cbd7bf24b0cc8efcfc66d8c5e7df4e27307
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305324"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="2d106-102">Vorgehensweise: Ändern von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d106-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="2d106-103">In diesem Thema erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ändern können.</span><span class="sxs-lookup"><span data-stu-id="2d106-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="2d106-104">Ausdrucksbaumstrukturen sind unveränderlich, d.h. sie können nicht direkt modifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="2d106-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="2d106-105">Um eine Ausdrucksbaumstruktur zu verändern, müssen Sie eine Kopie eines vorhandenen Ausdrucksbaumstruktur erstellen und währenddessen die erforderlichen Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2d106-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="2d106-106">Sie können die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse verwenden, um einen vorhandenen Ausdrucksbaum zu durchlaufen und jeden Knoten zu kopieren, der durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="2d106-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="2d106-107">So ändern Sie Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="2d106-107">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="2d106-108">Erstellen Sie ein neues **Konsolenanwendungsprojekt**.</span><span class="sxs-lookup"><span data-stu-id="2d106-108">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="2d106-109">Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.</span><span class="sxs-lookup"><span data-stu-id="2d106-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="2d106-110">Fügen Sie die `AndAlsoModifier`-Klasse in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="2d106-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="2d106-111">Diese Klasse erbt die <xref:System.Linq.Expressions.ExpressionVisitor>-Klasse und ist darauf spezialisiert, Ausdrücke zu verändern, die bedingte `AND`-Vorgänge darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d106-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="2d106-112">Es ändert diese Vorgänge von einem bedingten `AND` in ein bedingtes `OR`.</span><span class="sxs-lookup"><span data-stu-id="2d106-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="2d106-113">Zu diesem Zweck setzt die Klasse die <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>-Methode der Basisklasse außer Kraft, weil bedingte `AND`-Ausdrücke als binäre Ausdrücke dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d106-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="2d106-114">Für die `VisitBinary`-Methode gilt Folgendes: Wenn der an die Methode übergebene Ausdruck eine bedingte `AND`-Operation darstellt, erstellt der Code einen neuen Ausdruck, der den bedingten Operator `OR` anstelle des bedingten Operators `AND` enthält.</span><span class="sxs-lookup"><span data-stu-id="2d106-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="2d106-115">Wenn der an `VisitBinary` übergebene Ausdruck keinen bedingten `AND`-Vorgang darstellt, verzögert die Methode die Implementierung der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="2d106-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="2d106-116">Die Basisklassenmethode erstellt Knoten, die den übergebenen Ausdrucksbaumstrukturen gleichen. In diesem Fall sind die Teilstrukturen der Knoten jedoch durch die Ausdrucksbaumstrukturen ersetzt, die vom Besucher rekursiv erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d106-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="2d106-117">Hinzufügen einer `Imports` Anweisung, um die Datei für die `System.Linq.Expressions` Namespace.</span><span class="sxs-lookup"><span data-stu-id="2d106-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="2d106-118">Fügen Sie Code in die `Main` -Methode in der Datei "Module1.vb", um eine Ausdrucksbaumstruktur zu erstellen und übergeben es an die Methode, die Sie ändert.</span><span class="sxs-lookup"><span data-stu-id="2d106-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     <span data-ttu-id="2d106-119">Der Code erstellt einen Ausdruck, der einen bedingten `AND`-Vorgang enthält.</span><span class="sxs-lookup"><span data-stu-id="2d106-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="2d106-120">Er erstellt anschließend eine Instanz der `AndAlsoModifier`-Klasse und übergibt den Ausdruck an die `Modify`-Methode dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d106-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="2d106-121">Sowohl der ursprüngliche als auch der geänderte Ausdrucksbaum werden ausgegeben, um die Änderungen zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="2d106-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="2d106-122">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="2d106-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d106-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d106-123">See also</span></span>

- [<span data-ttu-id="2d106-124">Vorgehensweise: Ausführen von Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d106-124">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [<span data-ttu-id="2d106-125">Ausdrucksbaumstrukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d106-125">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
