---
title: Using-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 819af63acb6a1f038300bcb999dcfb904eb8a457
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592088"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="f44dc-102">Using-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f44dc-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="f44dc-103">Deklariert den Anfang eines `Using`-Blocks und ruft optional die Systemressourcen ab, die der Block steuert.</span><span class="sxs-lookup"><span data-stu-id="f44dc-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="f44dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f44dc-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="f44dc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f44dc-105">Parts</span></span>

|<span data-ttu-id="f44dc-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f44dc-106">Term</span></span>|<span data-ttu-id="f44dc-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f44dc-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="f44dc-108">Erforderlich, wenn Sie `resourceexpression` nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="f44dc-109">Liste mit mindestens einer System Ressource, die von diesem `Using`-Block gesteuert wird, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="f44dc-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="f44dc-110">Erforderlich, wenn Sie `resourcelist` nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="f44dc-111">Verweis Variable oder-Ausdruck, der auf eine System Ressource verweist, die von diesem `Using`-Block gesteuert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f44dc-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="f44dc-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="f44dc-112">Optional.</span></span> <span data-ttu-id="f44dc-113">Block von-Anweisungen, die der `Using`-Block ausführt.</span><span class="sxs-lookup"><span data-stu-id="f44dc-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="f44dc-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f44dc-114">Required.</span></span> <span data-ttu-id="f44dc-115">Beendet die Definition des `Using`-Blocks und gibt alle von ihm kontrollierten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="f44dc-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="f44dc-116">Jede Ressource im `resourcelist`-Teil weist die folgende Syntax und Teile auf:</span><span class="sxs-lookup"><span data-stu-id="f44dc-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="f44dc-117">- oder -</span><span class="sxs-lookup"><span data-stu-id="f44dc-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="f44dc-118">resourceList-Teile</span><span class="sxs-lookup"><span data-stu-id="f44dc-118">resourcelist Parts</span></span>

|<span data-ttu-id="f44dc-119">Begriff</span><span class="sxs-lookup"><span data-stu-id="f44dc-119">Term</span></span>|<span data-ttu-id="f44dc-120">Definition</span><span class="sxs-lookup"><span data-stu-id="f44dc-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="f44dc-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f44dc-121">Required.</span></span> <span data-ttu-id="f44dc-122">Verweis Variable, die auf eine System Ressource verweist, die von der `Using` blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="f44dc-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="f44dc-123">Erforderlich, wenn die `Using`-Anweisung die Ressource abruft.</span><span class="sxs-lookup"><span data-stu-id="f44dc-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="f44dc-124">Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.</span><span class="sxs-lookup"><span data-stu-id="f44dc-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="f44dc-125">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f44dc-125">Required.</span></span> <span data-ttu-id="f44dc-126">Die Klasse der Ressource.</span><span class="sxs-lookup"><span data-stu-id="f44dc-126">The class of the resource.</span></span> <span data-ttu-id="f44dc-127">Die-Klasse muss die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="f44dc-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="f44dc-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="f44dc-128">Optional.</span></span> <span data-ttu-id="f44dc-129">Liste von Argumenten, die Sie an den Konstruktor übergeben, um eine Instanz von `resourcetype` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="f44dc-130">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="f44dc-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="f44dc-131">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f44dc-131">Required.</span></span> <span data-ttu-id="f44dc-132">Eine Variable oder ein Ausdruck, der auf eine System Ressource verweist, die die Anforderungen von `resourcetype` erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f44dc-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="f44dc-133">Wenn Sie die zweite Syntax Alternative verwenden, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f44dc-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f44dc-134">Remarks</span></span>

 <span data-ttu-id="f44dc-135">Manchmal erfordert Ihr Code eine nicht verwaltete Ressource, z. b. ein Datei Handle, einen COM-Wrapper oder eine SQL-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f44dc-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="f44dc-136">Ein `Using`-Block gewährleistet, dass mindestens eine solche Ressource freigegeben wird, wenn der Code damit fertig ist.</span><span class="sxs-lookup"><span data-stu-id="f44dc-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="f44dc-137">Dies macht Sie für anderen Code verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f44dc-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="f44dc-138">Verwaltete Ressourcen werden vom .NET Framework Garbage Collector (GC) verworfen, ohne dass zusätzliche Codierungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f44dc-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="f44dc-139">Sie benötigen keinen `Using`-Block für verwaltete Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="f44dc-140">Sie können jedoch weiterhin einen `Using`-Block verwenden, um die Freigabe einer verwalteten Ressource zu erzwingen, anstatt auf die Garbage Collector zu warten.</span><span class="sxs-lookup"><span data-stu-id="f44dc-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="f44dc-141">Ein `Using`-Block besteht aus drei Teilen: Erwerb, Verwendung und Entsorgung.</span><span class="sxs-lookup"><span data-stu-id="f44dc-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="f44dc-142">Der *Erwerb* bedeutet, dass eine Variable erstellt und initialisiert wird, um auf die System Ressource zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="f44dc-143">Mit der `Using`-Anweisung können Sie eine oder mehrere Ressourcen abrufen, oder Sie können genau eine Ressource abrufen, bevor Sie den Block eingeben und für die `Using`-Anweisung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="f44dc-144">Wenn Sie `resourceexpression` angeben, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="f44dc-145">*Verwendung* bedeutet, dass auf die Ressourcen zugegriffen und Aktionen mit Ihnen durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f44dc-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="f44dc-146">Die Anweisungen zwischen `Using` und `End Using` stellen die Verwendung der Ressourcen dar.</span><span class="sxs-lookup"><span data-stu-id="f44dc-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="f44dc-147">Die *Beseitigung* bedeutet, dass die <xref:System.IDisposable.Dispose%2A>-Methode für das Objekt in `resourcename` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f44dc-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="f44dc-148">Dies ermöglicht es dem-Objekt, seine Ressourcen ordnungsgemäß zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f44dc-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="f44dc-149">Die `End Using`-Anweisung gibt die Ressourcen unter der Steuerung des `Using`-Blocks frei.</span><span class="sxs-lookup"><span data-stu-id="f44dc-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="f44dc-150">Verhalten</span><span class="sxs-lookup"><span data-stu-id="f44dc-150">Behavior</span></span>

 <span data-ttu-id="f44dc-151">Ein `Using`-Block verhält sich wie eine `Try`... `Finally`-Konstruktion, in der der `Try`-Block die Ressourcen verwendet und der `Finally`-Block diese freigibt.</span><span class="sxs-lookup"><span data-stu-id="f44dc-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="f44dc-152">Aus diesem Grund garantiert der `Using`-Block die Beseitigung der Ressourcen, unabhängig davon, wie Sie den Block beenden.</span><span class="sxs-lookup"><span data-stu-id="f44dc-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="f44dc-153">Dies gilt auch im Fall einer nicht behandelten Ausnahme, mit Ausnahme eines <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="f44dc-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="f44dc-154">Der Gültigkeitsbereich jeder Ressourcenvariablen, die durch die `Using`-Anweisung abgerufen wird, ist auf den Block "`Using`" beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f44dc-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="f44dc-155">Wenn Sie in der `Using`-Anweisung mehr als eine System Ressource angeben, ist der Effekt identisch mit der geschachtelten `Using`-Blöcke innerhalb einer anderen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="f44dc-156">Wenn `resourcename` `Nothing` ist, wird kein-<xref:System.IDisposable.Dispose%2A>-aufgerufen, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f44dc-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="f44dc-157">Strukturierte Ausnahmebehandlung innerhalb eines using-Blocks</span><span class="sxs-lookup"><span data-stu-id="f44dc-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="f44dc-158">Wenn Sie eine Ausnahme behandeln müssen, die möglicherweise im `Using`-Block auftritt, können Sie eine komplette `Try`... `Finally`-Konstruktion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="f44dc-159">Wenn Sie den Fall behandeln müssen, in dem die `Using`-Anweisung beim Abrufen einer Ressource nicht erfolgreich ist, können Sie prüfen, ob `resourcename` `Nothing` ist.</span><span class="sxs-lookup"><span data-stu-id="f44dc-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="f44dc-160">Strukturierte Ausnahmebehandlung anstelle eines using-Blocks</span><span class="sxs-lookup"><span data-stu-id="f44dc-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="f44dc-161">Wenn Sie eine präzisere Kontrolle über die Beschaffung der Ressourcen benötigen oder zusätzlichen Code im `Finally`-Block benötigen, können Sie den `Using`-Block als `Try`... `Finally`-Konstruktion umschreiben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="f44dc-162">Im folgenden Beispiel werden Skeleton `Try`-und `Using`-Konstruktionen veranschaulicht, die im Erwerb und der Entsorgung von `resource` gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="f44dc-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

```vb
Using resource As New resourceType
    ' Insert code to work with resource.
End Using

' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.
Dim resource As New resourceType
Try
    ' Insert code to work with resource.
Finally
    If resource IsNot Nothing Then
        resource.Dispose()
    End If
End Try
```

> [!NOTE]
> <span data-ttu-id="f44dc-163">Der Code innerhalb des `Using`-Blocks sollte das Objekt in `resourcename` nicht einer anderen Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f44dc-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="f44dc-164">Wenn Sie den `Using`-Block beenden, wird die Ressource verworfen, und die andere Variable kann nicht auf die Ressource zugreifen, auf die Sie verweist.</span><span class="sxs-lookup"><span data-stu-id="f44dc-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="f44dc-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f44dc-165">Example</span></span>

 <span data-ttu-id="f44dc-166">Im folgenden Beispiel wird eine Datei mit dem Namen Log. txt erstellt, und es werden zwei Textzeilen in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f44dc-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="f44dc-167">Das Beispiel liest auch dieselbe Datei und zeigt die Textzeilen an:</span><span class="sxs-lookup"><span data-stu-id="f44dc-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="f44dc-168">Da die Klassen <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> die <xref:System.IDisposable>-Schnittstelle implementieren, kann der Code `Using`-Anweisungen verwenden, um sicherzustellen, dass die Datei nach den Schreib-und Lesevorgängen ordnungsgemäß geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f44dc-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="f44dc-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f44dc-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="f44dc-170">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f44dc-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- <span data-ttu-id="f44dc-171">[Vorgehensweise: Verwerfen einer System Ressource @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="f44dc-171">[How to: Dispose of a System Resource](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)</span></span>
