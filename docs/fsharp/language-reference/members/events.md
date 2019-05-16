---
title: Ereignisse
description: Erfahren Sie, wie F# Ereignisse ermöglichen, die in der GUI-Programmierung wichtig sind Benutzeraktionen Funktionsaufrufe zugeordnet werden soll.
ms.date: 05/16/2016
ms.openlocfilehash: ad2e8001b81f48fdeb783bee2423a3dc9e22ac79
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645223"
---
# <a name="events"></a><span data-ttu-id="f6fc9-103">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f6fc9-103">Events</span></span>

> [!NOTE]
> <span data-ttu-id="f6fc9-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f6fc9-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f6fc9-106">Mit Ereignissen ordnen Sie Benutzeraktionen Funktionsaufrufe zu. Sie sind wichtig in der GUI-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-106">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="f6fc9-107">Ereignisse können auch von den Anwendungen oder dem Betriebssystem ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-107">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="f6fc9-108">Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="f6fc9-108">Handling Events</span></span>

<span data-ttu-id="f6fc9-109">Wenn Sie eine GUI-Bibliothek, z. B. Windows Forms oder Windows Presentation Foundation (WPF), verwenden, wird ein großer Anteil des Codes in der Anwendung aufgrund von Ereignissen ausgeführt, die durch die Bibliothek vordefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-109">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="f6fc9-110">Diese vordefinierten Ereignisse sind Member von GUI-Klassen, z. B. Forms und Control.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-110">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="f6fc9-111">Sie können einem bereits vorhandenen Ereignis benutzerdefiniertes Verhalten, z. B. das Klicken auf eine Schaltfläche, hinzufügen, indem Sie auf das entsprechende Ereignis (z. B. das `Click`-Ereignis der `Form`-Klasse) verweisen und die `Add`-Methode aufrufen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-111">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="f6fc9-112">Lassen Sie bei der Ausführung in F# Interactive den Aufruf von `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` weg.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-112">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="f6fc9-113">Der Typ der `Add`-Methode ist `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-113">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="f6fc9-114">Daher akzeptiert die Ereignishandlermethode einen Parameter, in der Regel die Ereignisargumente, und gibt `unit` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-114">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="f6fc9-115">Im vorherigen Beispiel ist der Ereignishandler ein Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-115">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="f6fc9-116">Der Ereignishandler kann auch ein Funktionswert sein, wie im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-116">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="f6fc9-117">Im folgenden Codebeispiel wird auch die Verwendung der Ereignishandlerparameter veranschaulicht, die spezifische Informationen für den Typ des Ereignisses bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-117">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="f6fc9-118">Für ein `MouseMove`-Ereignis übergibt das System ein `System.Windows.Forms.MouseEventArgs`-Objekt, das die `X`- und `Y`-Position des Zeigers enthält.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-118">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="f6fc9-119">Erstellen von benutzerdefinierten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="f6fc9-119">Creating Custom Events</span></span>

<span data-ttu-id="f6fc9-120">F#Ereignisse werden dargestellt, durch die F# [Ereignis](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) Klasse implementiert die [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-120">F# events are represented by the F# [Event](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) class, which implements the [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interface.</span></span> <span data-ttu-id="f6fc9-121">`IEvent` ist eine Schnittstelle, die kombiniert die Funktionalität zweier anderer Schnittstellen `System.IObservable<'T>` und [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span><span class="sxs-lookup"><span data-stu-id="f6fc9-121">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span></span> <span data-ttu-id="f6fc9-122">Daher verfügen `Event`s über die gleiche Funktionalität wie Delegaten in anderen Sprachen und zusätzlich über die Funktionen von `IObservable`. F#-Ereignisse unterstützen somit die Ereignisfilterung und das Verwenden von F#-Funktionen der ersten Klasse und von Lambdaausdrücken als Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-122">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="f6fc9-123">Diese Funktionalität wird bereitgestellt, der [Event-Modul](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span><span class="sxs-lookup"><span data-stu-id="f6fc9-123">This functionality is provided in the [Event module](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span></span>

<span data-ttu-id="f6fc9-124">Zum Erstellen eines Ereignisses für eine Klasse, das sich wie ein beliebiges anderes .NET Framework-Ereignis verhält, fügen Sie der Klasse eine `let`-Bindung hinzu, die ein `Event` als Feld in einer Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-124">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="f6fc9-125">Sie können den gewünschten Ereignisargumenttyp als Typargument angeben oder den Wert freilassen und einen geeigneten Wert durch den Compiler bestimmen lassen.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-125">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="f6fc9-126">Sie müssen außerdem einen Ereignismember definieren, der das Ereignis als CLI-Ereignis verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-126">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="f6fc9-127">Dieser Member müssen die [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) Attribut.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-127">This member should have the [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attribute.</span></span> <span data-ttu-id="f6fc9-128">Wird es wie eine Eigenschaft deklariert, und seine Implementierung ist einfach einen Aufruf der [veröffentlichen](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) Eigenschaft des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-128">It is declared like a property and its implementation is just a call to the [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) property of the event.</span></span> <span data-ttu-id="f6fc9-129">Benutzer der Klasse können die `Add`-Methode des veröffentlichten Ereignisses verwenden, um einen Handler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-129">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="f6fc9-130">Das Argument für die `Add`-Methode kann ein Lambda-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-130">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="f6fc9-131">Sie können die `Trigger`-Eigenschaft des Ereignisses verwenden, um das Ereignis auszulösen und das Argument an die Handlerfunktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-131">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="f6fc9-132">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-132">The following code example illustrates this.</span></span> <span data-ttu-id="f6fc9-133">In diesem Beispiel ist das abgeleitete Typargument für das Ereignis ein Tupel, das die Argumente für den Lambda-Ausdruck darstellt.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-133">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="f6fc9-134">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-134">The output is as follows.</span></span>

```
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="f6fc9-135">Die zusätzliche vom `Event`-Modul bereitgestellte Funktionalität wird hier veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-135">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="f6fc9-136">Im folgenden Codebeispiel wird die grundlegende Verwendung von `Event.create` zur Erstellung eines Ereignisses und einer Triggermethode, zum Hinzufügen zweier Ereignishandler in der Form von Lambdaausdrücken und dem Auslösen des Ereignisses zur Ausführung beider Lambdaausdrücke dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-136">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="f6fc9-137">Der obige Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-137">The output of the previous code is as follows.</span></span>

```
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="f6fc9-138">Verarbeiten von Ereignisstreams</span><span class="sxs-lookup"><span data-stu-id="f6fc9-138">Processing Event Streams</span></span>

<span data-ttu-id="f6fc9-139">Statt einfach einen Ereignishandler für ein Ereignis mithilfe der [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) -Funktion können Sie die Funktionen in der `Event` Modul, um ereignisdatenströme Prozess Ereignisstreams hochgradig Benutzerdefiniert.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-139">Instead of just adding an event handler for an event by using the [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="f6fc9-140">Hierzu verwenden Sie den Vorwärtspipeoperator (`|>`) zusammen mit dem Ereignis als ersten Wert in einer Reihe von Funktionsaufrufen und die `Event`-Modulfunktionen als nachfolgende Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-140">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="f6fc9-141">Im folgenden Codebeispiel wird die Einrichtung eines Ereignisses gezeigt, für das der Handler nur unter bestimmten Bedingungen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-141">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="f6fc9-142">Die [Observable-Modul](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) enthält ähnliche Funktionen, die auf Observable-Objekte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-142">The [Observable module](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="f6fc9-143">Observable-Objekte sind Ereignissen ähnlich, abonnieren Ereignisse aber nur, wenn sie selbst abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-143">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="f6fc9-144">Implementieren eines Schnittstellenereignisses</span><span class="sxs-lookup"><span data-stu-id="f6fc9-144">Implementing an Interface Event</span></span>

<span data-ttu-id="f6fc9-145">Häufig beginnen Sie beim Entwickeln von UI-Komponenten, indem Sie ein neues Formular oder ein neues Steuerelement erstellen, das von einem vorhandenen Formular oder Steuerelement erbt.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-145">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="f6fc9-146">Ereignisse werden oft für eine Schnittstelle definiert, und in diesem Fall müssen Sie die Schnittstelle implementieren, um das Ereignis zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-146">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="f6fc9-147">Die `System.ComponentModel.INotifyPropertyChanged`-Schnittstelle definiert ein einzelnes `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f6fc9-147">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="f6fc9-148">Der folgende Code veranschaulicht die Implementierung des Ereignisses, das von dieser geerbten Schnittstelle definiert wurde:</span><span class="sxs-lookup"><span data-stu-id="f6fc9-148">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="f6fc9-149">Wenn Sie das Ereignis im Konstruktor einbinden möchten, ist der Code etwas komplizierter, da sich die Ereignisverknüpfung wie im folgenden Beispiel in einem `then`-Block in einem zusätzlichen Konstruktor befinden muss:</span><span class="sxs-lookup"><span data-stu-id="f6fc9-149">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")

    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="f6fc9-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6fc9-150">See also</span></span>

- [<span data-ttu-id="f6fc9-151">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="f6fc9-151">Members</span></span>](index.md)
- [<span data-ttu-id="f6fc9-152">Behandeln und Auslösen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="f6fc9-152">Handling and Raising Events</span></span>](../../../../docs/standard/events/index.md)
- [<span data-ttu-id="f6fc9-153">Lambda-Ausdrücke: Das `fun`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="f6fc9-153">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
- [<span data-ttu-id="f6fc9-154">Control.Event-Modul</span><span class="sxs-lookup"><span data-stu-id="f6fc9-154">Control.Event Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [<span data-ttu-id="f6fc9-155">Control.Event&#60;t&#62; Klasse</span><span class="sxs-lookup"><span data-stu-id="f6fc9-155">Control.Event&#60;'T&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [<span data-ttu-id="f6fc9-156">Control.Event&#60;'Delegate,'Args&#62; Class</span><span class="sxs-lookup"><span data-stu-id="f6fc9-156">Control.Event&#60;'Delegate,'Args&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
