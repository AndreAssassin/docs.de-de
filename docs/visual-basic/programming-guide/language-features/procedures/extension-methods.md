---
title: Erweiterungsmethoden (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 9e005d0dc7da154fbaffbf7e02c55445a1213195
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296237"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="88442-102">Erweiterungsmethoden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88442-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="88442-103">Erweiterungsmethoden ermöglichen Entwicklern das Hinzufügen von benutzerdefinierten Funktionen, Datentypen, die bereits definiert sind, ohne einen neuen abgeleiteten Typ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88442-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="88442-104">Erweiterungsmethoden ermöglichen das Schreiben eine Methode, die aufgerufen werden können, als handele es sich um eine Instanzenmethode des vorhandenen Typs.</span><span class="sxs-lookup"><span data-stu-id="88442-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88442-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88442-105">Remarks</span></span>  
 <span data-ttu-id="88442-106">Eine Erweiterungsmethode kann ausschließlich eine `Sub`-Prozedur oder eine `Function`-Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="88442-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="88442-107">Erweiterungseigenschaften, -felder oder -ereignisse können nicht definiert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="88442-108">Alle Erweiterungsmethoden müssen mit dem Erweiterungsattribut `<Extension()>` aus dem <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace markiert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="88442-109">Der erste Parameter in der Definition einer Erweiterungsmethode gibt den Datentyp an, der von der Methode erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="88442-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="88442-110">Beim Ausführen der Methode wird der erste Parameter an die Instanz des Datentyps gebunden, der die Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="88442-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88442-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88442-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="88442-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88442-112">Description</span></span>  
 <span data-ttu-id="88442-113">Im folgenden Beispiel wird eine `Print`-Erweiterung für den <xref:System.String>-Datentyp definiert.</span><span class="sxs-lookup"><span data-stu-id="88442-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="88442-114">Die Methode verwendet `Console.WriteLine`, um eine Zeichenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88442-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="88442-115">Durch den `Print`-Parameter der `aString`-Methode wird festgelegt, dass die <xref:System.String>-Klasse von der Methode erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="88442-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 <span data-ttu-id="88442-116">Beachten Sie, dass die Definition der Erweiterungsmethode mit dem Erweiterungsattribut `<Extension()>` markiert ist.</span><span class="sxs-lookup"><span data-stu-id="88442-116">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="88442-117">Die Markierung des Moduls, in dem die Methode definiert ist, ist optional, aber jede Erweiterungsmethode muss markiert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-117">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="88442-118">Zum Zugriff auf das Erweiterungsattribut muss <xref:System.Runtime.CompilerServices> importiert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-118"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="88442-119">Erweiterungsmethoden können nur innerhalb von Modulen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-119">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="88442-120">Bei dem Modul, in dem eine Erweiterungsmethode definiert wird, handelt es sich normalerweise um ein anderes Modul als das, in dem sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="88442-120">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="88442-121">Stattdessen wird das Modul, in dem die Erweiterungsmethode enthalten ist, ggf. importiert, um es in den Gültigkeitsbereich einzubinden.</span><span class="sxs-lookup"><span data-stu-id="88442-121">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="88442-122">Nachdem sich das Modul, in dem `Print` enthalten ist, im Gültigkeitsbereich befindet, kann die Methode wie jede andere gewöhnliche Instanzenmethode, die keine Argumente verwendet (z. B. `ToUpper`) aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="88442-122">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 <span data-ttu-id="88442-123">Das nächste Beispiel, `PrintAndPunctuate`, ist auch eine Erweiterung für <xref:System.String> und wird dieses Mal mit zwei Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="88442-123">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="88442-124">Der erste Parameter, `aString`, legt fest, dass die Erweiterungsmethode <xref:System.String> erweitert.</span><span class="sxs-lookup"><span data-stu-id="88442-124">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="88442-125">Mit dem zweiten Parameter, `punc`, wird eine aus Satzzeichen bestehende Zeichenfolge bereitgestellt, die beim Aufruf der Methode als Argument übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="88442-125">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="88442-126">Durch die Methode wird die Zeichenfolge gefolgt von den Satzzeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88442-126">The method displays the string followed by the punctuation marks.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 <span data-ttu-id="88442-127">Die Methode wird aufgerufen, indem ein Zeichenfolgenargument für `punc` gesendet wird: `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="88442-127">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="88442-128">Im folgenden Beispiel werden `Print` und `PrintAndPunctuate` definiert und aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="88442-128">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="88442-129"><xref:System.Runtime.CompilerServices> wird in das Definitionsmodul importiert, um den Zugriff auf das Erweiterungsattribut zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="88442-129"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88442-130">Code</span><span class="sxs-lookup"><span data-stu-id="88442-130">Code</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="88442-131">Als Nächstes werden die Erweiterungsmethoden in den Gültigkeitsbereich eingebunden und aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="88442-131">Next, the extension methods are brought into scope and called.</span></span>  
  
```vb  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="88442-132">Kommentare</span><span class="sxs-lookup"><span data-stu-id="88442-132">Comments</span></span>  
 <span data-ttu-id="88442-133">Die einzige Voraussetzung für das Ausführen dieser oder ähnlicher Erweiterungsmethoden besteht darin, dass sie sich innerhalb des Gültigkeitsbereichs befinden müssen.</span><span class="sxs-lookup"><span data-stu-id="88442-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="88442-134">Wenn sich das Modul mit einer Erweiterungsmethode im Gültigkeitsbereich befindet, ist es für IntelliSense erkennbar und kann wie jede andere gewöhnliche Instanzenmethode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="88442-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="88442-135">Beachten Sie, dass beim Aufrufen der Methoden kein Argument für den ersten Parameter gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="88442-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="88442-136">Der `aString`-Parameter in den vorherigen Methodendefinitionen ist an `example` gebunden, also die Instanz von `String`, durch die sie aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="88442-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="88442-137">Der Compiler verwendet `example` als das an den ersten Parameter gesendete Argument.</span><span class="sxs-lookup"><span data-stu-id="88442-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="88442-138">Wenn eine Erweiterungsmethode für ein Objekt aufgerufen wird, das auf `Nothing` festgelegt ist, wird die Erweiterungsmethode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88442-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="88442-139">Dies trifft nicht auf normale Instanzmethoden zu.</span><span class="sxs-lookup"><span data-stu-id="88442-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="88442-140">Sie können in der Erweiterungsmethode explizit auf `Nothing` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="88442-140">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="88442-141">Erweiterungsfähige Typen</span><span class="sxs-lookup"><span data-stu-id="88442-141">Types That Can Be Extended</span></span>  
 <span data-ttu-id="88442-142">Erweiterungsmethoden können für die meisten Typen definiert werden, die in Visual Basic-Parameterlisten wie den folgenden dargestellt werden können:</span><span class="sxs-lookup"><span data-stu-id="88442-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="88442-143">Klassen (Referenztypen)</span><span class="sxs-lookup"><span data-stu-id="88442-143">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="88442-144">Strukturen (Werttypen)</span><span class="sxs-lookup"><span data-stu-id="88442-144">Structures (value types)</span></span>  
  
-   <span data-ttu-id="88442-145">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="88442-145">Interfaces</span></span>  
  
-   <span data-ttu-id="88442-146">Delegaten</span><span class="sxs-lookup"><span data-stu-id="88442-146">Delegates</span></span>  
  
-   <span data-ttu-id="88442-147">ByRef- und ByVal-Argumente</span><span class="sxs-lookup"><span data-stu-id="88442-147">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="88442-148">Parameter für generische Methoden</span><span class="sxs-lookup"><span data-stu-id="88442-148">Generic method parameters</span></span>  
  
-   <span data-ttu-id="88442-149">Arrays</span><span class="sxs-lookup"><span data-stu-id="88442-149">Arrays</span></span>  
  
 <span data-ttu-id="88442-150">Da der erste Parameter den Datentyp angibt, der durch die Erweiterungsmethode erweitert wird, ist er erforderlich und kann nicht ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="88442-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="88442-151">Aus diesem Grund kann ein `Optional`-Parameter oder ein `ParamArray`-Parameter nicht der erste Parameter in der Parameterliste sein.</span><span class="sxs-lookup"><span data-stu-id="88442-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="88442-152">Erweiterungsmethoden werden bei der späten Bindung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="88442-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="88442-153">Im folgenden Beispiel löst die `anObject.PrintMe()`-Anweisung eine <xref:System.MissingMemberException>-Ausnahme aus. Dieselbe Ausnahme wird angezeigt, wenn die zweite `PrintMe`-Erweiterungsmethodendefinition gelöscht würde.</span><span class="sxs-lookup"><span data-stu-id="88442-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a><span data-ttu-id="88442-154">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="88442-154">Best Practices</span></span>  
 <span data-ttu-id="88442-155">Erweiterungsmethoden bieten eine einfache und leistungsstarke Möglichkeit zur Erweiterung eines vorhandenen Typs.</span><span class="sxs-lookup"><span data-stu-id="88442-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="88442-156">Um sie erfolgreich zu verwenden, sind jedoch einige Punkte zu beachten.</span><span class="sxs-lookup"><span data-stu-id="88442-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="88442-157">Obwohl sich diese Überlegungen hauptsächlich auf Autoren von Klassenbibliotheken beziehen, können sie gleichzeitig Anwendungen betreffen, die Erweiterungsmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="88442-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="88442-158">Erweiterungsmethoden, die Sie Typen hinzufügen, die sich nicht in Ihrem Besitz befinden, sind im Allgemeinen angreifbarer als Erweiterungsmethoden, die Sie Typen hinzufügen, die von Ihnen gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="88442-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="88442-159">In Klassen, die sich nicht in Ihrem Besitz befinden, können einige Ereignisse auftreten, die Ihre Erweiterungsmethoden negativ beeinflussen könnten.</span><span class="sxs-lookup"><span data-stu-id="88442-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="88442-160">Falls ein Instanzenmember vorhanden ist, auf den zugegriffen werden kann und der über eine mit den Argumenten in der aufrufenden Anweisung kompatible Signatur verfügt, ohne dass einschränkende Konvertierungen vom Argument zum Parameter festgelegt sind, wird die Instanzenmethode vor allen Erweiterungsmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="88442-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="88442-161">Daher ist es möglich, dass auf einen vorhandenen Erweiterungsmember, den Sie verwenden möchten, nicht mehr zugegriffen werden kann, wenn einer Klasse zu einem bestimmten Zeitpunkt eine geeignete Instanzenmethode hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="88442-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="88442-162">Der Autor einer Erweiterungsmethode kann nicht verhindern, dass andere Programmierer Erweiterungsmethoden schreiben, die Vorrang vor der ursprünglichen Erweiterung haben und damit Konflikte verursachen.</span><span class="sxs-lookup"><span data-stu-id="88442-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="88442-163">Sie können die Stabilität verbessern, indem Sie Erweiterungsmethoden in einen eigenen Namespace einfügen.</span><span class="sxs-lookup"><span data-stu-id="88442-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="88442-164">Consumer Ihrer Bibliothek können einen Namespace dann ein- oder ausschließen bzw. vom Rest der Bibliothek getrennt unter den Namespaces auswählen.</span><span class="sxs-lookup"><span data-stu-id="88442-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="88442-165">Das Erweitern von Schnittstellen bietet u. U. mehr Sicherheit als das Erweitern von Klassen, insbesondere, wenn Sie nicht der Besitzer der Schnittstelle oder Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="88442-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="88442-166">Eine Änderung einer Schnittstelle wirkt sich auf jede Klasse aus, die von ihr implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="88442-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="88442-167">Deshalb ist es eher unwahrscheinlich, dass der Autor Methoden in einer Schnittstelle hinzufügt oder ändert.</span><span class="sxs-lookup"><span data-stu-id="88442-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="88442-168">Wenn eine Klasse jedoch zwei Schnittstellen implementiert, die über Erweiterungsmethoden mit gleicher Signatur verfügen, wird keine der Erweiterungsmethoden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88442-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="88442-169">Erweitern Sie einen möglichst spezifischen Typ.</span><span class="sxs-lookup"><span data-stu-id="88442-169">Extend the most specific type you can.</span></span> <span data-ttu-id="88442-170">Wenn Sie in einer Typhierarchie einen Typ auswählen, von dem viele andere Typen abgeleitet sind, können auf viele Weisen Instanzenmethoden oder andere Erweiterungsmethoden eingeführt werden, die Konflikte mit Ihren Instanzen- oder Erweiterungsmethoden verursachen könnten.</span><span class="sxs-lookup"><span data-stu-id="88442-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="88442-171">Erweiterungsmethoden, Instanzmethoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="88442-171">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="88442-172">Wenn eine Instanzmethode im Gültigkeitsbereich über eine Signatur verfügt, die mit den Argumenten einer Aufrufanweisung kompatibel ist, wird die Instanzmethode vor den Erweiterungsmethoden bevorzugt ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="88442-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="88442-173">Die Instanzmethode hat auch dann Vorrang, wenn die Erweiterungsmethode eine bessere Übereinstimmung aufweist.</span><span class="sxs-lookup"><span data-stu-id="88442-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="88442-174">Im folgenden Beispiel enthält die `ExampleClass` eine Instanzmethode mit der Bezeichnung `ExampleMethod`, die über einen Parameter des Typs `Integer` verfügt.</span><span class="sxs-lookup"><span data-stu-id="88442-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="88442-175">Die Erweiterungsmethode `ExampleMethod` erweitert die `ExampleClass` und verfügt über einen Parameter des Typs `Long`.</span><span class="sxs-lookup"><span data-stu-id="88442-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 <span data-ttu-id="88442-176">Mit dem ersten Aufruf an `ExampleMethod` im folgenden Code wird die Erweiterungsmethode aufgerufen, da `arg1` den Wert `Long` hat und nur mit dem `Long`-Parameter in der Erweiterungsmethode kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="88442-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="88442-177">Der zweite Aufruf von `ExampleMethod` verfügt über ein `Integer`-Argument, `arg2`, und es ruft die Instanzmethode auf.</span><span class="sxs-lookup"><span data-stu-id="88442-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 <span data-ttu-id="88442-178">Kehren Sie nun die Datentypen der Parameter in den zwei Methoden um:</span><span class="sxs-lookup"><span data-stu-id="88442-178">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 <span data-ttu-id="88442-179">Dieses Mal ruft der Code in `Main` beide Male die Instanzmethode auf.</span><span class="sxs-lookup"><span data-stu-id="88442-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="88442-180">Das liegt daran, dass sowohl `arg1` und `arg2` über eine Erweiterungskonvertierung zu `Long` verfügen, und die Instanzmethode in beiden Fällen Vorrang vor der Erweiterungsmethode hat.</span><span class="sxs-lookup"><span data-stu-id="88442-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 <span data-ttu-id="88442-181">Dies bedeutet, dass eine Erweiterungsmethode keine vorhandene Instanzmethode ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="88442-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="88442-182">Wenn eine Erweiterungsmethode jedoch über denselben Namen wie eine Instanzmethode verfügt, die Signaturen aber keine Konflikte verursachen, kann auf beide Methoden zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="88442-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="88442-183">Wenn die `ExampleClass` beispielsweise eine Methode mit dem Namen `ExampleMethod` enthält, die keine Argumente verwendet, sind Erweiterungsmethoden mit demselben Namen aber unterschiedlichen Signaturen zulässig, wie in folgendem Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="88442-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 <span data-ttu-id="88442-184">Dieser Code generiert folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="88442-184">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="88442-185">Bezüglich Eigenschaften ist der Sachverhalt unkomplizierter: Wenn eine Erweiterungsmethode den gleichen Namen wie eine Eigenschaft der Klasse hat, die sie erweitert, wird die Erweiterungsmethode nicht angezeigt, und es kann nicht darauf zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="88442-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="88442-186">Rangfolge von Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="88442-186">Extension Method Precedence</span></span>  
 <span data-ttu-id="88442-187">Wenn sich zwei Erweiterungsmethoden mit identischen Signaturen im Gültigkeitsbereich befinden und zugreifbar sind, wird die Methode mit der höheren Rangfolge aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="88442-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="88442-188">Die Rangfolge einer Erweiterungsmethode basiert auf dem Mechanismus, der verwendet wird, um die Methode in den Gültigkeitsbereich einzubinden.</span><span class="sxs-lookup"><span data-stu-id="88442-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="88442-189">Die folgende Liste gibt die hierarchische Rangfolge von oben nach unten an:</span><span class="sxs-lookup"><span data-stu-id="88442-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1. <span data-ttu-id="88442-190">Im aktuellen Modul definierte Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="88442-190">Extension methods defined inside the current module.</span></span>  
  
2. <span data-ttu-id="88442-191">Erweiterungsmethoden, die innerhalb von Datentypen im aktuellen Namespace oder in übergeordneten Namespaces definiert sind, wobei untergeordnete Namespaces eine höhere Rangfolge als übergeordnete Namespaces haben.</span><span class="sxs-lookup"><span data-stu-id="88442-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3. <span data-ttu-id="88442-192">In Typimporten in der aktuellen Datei definierte Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="88442-192">Extension methods defined inside any type imports in the current file.</span></span>  
  
4. <span data-ttu-id="88442-193">In Namespaceimporten in der aktuellen Datei definierte Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="88442-193">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5. <span data-ttu-id="88442-194">In Typimporten auf Projektebene definierte Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="88442-194">Extension methods defined inside any project-level type imports.</span></span>  
  
6. <span data-ttu-id="88442-195">In Namespaceimporten auf Projektebene definierte Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="88442-195">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="88442-196">Wenn sich die Mehrdeutigkeit durch die Anwendung einer Rangfolge nicht auflösen lässt, können Sie den vollqualifizierten Namen zum Festlegen der aufgerufenen Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="88442-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="88442-197">Wenn die `Print`-Methode aus dem vorherigen Beispiel in einem Modul mit dem Namen `StringExtensions` definiert wird, lautet der vollqualifizierte Name `StringExtensions.Print(example)` und nicht `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="88442-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88442-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88442-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="88442-199">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="88442-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="88442-200">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="88442-200">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="88442-201">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="88442-201">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="88442-202">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="88442-202">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="88442-203">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="88442-203">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="88442-204">Übersicht über Attribute</span><span class="sxs-lookup"><span data-stu-id="88442-204">Attributes overview</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="88442-205">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88442-205">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
